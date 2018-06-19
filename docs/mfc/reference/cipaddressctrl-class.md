---
title: Класс CIPAddressCtrl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
dev_langs:
- C++
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86d6c4cdff533538c2f0ea7f0be1fa44bfd27359
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368918"
---
# <a name="cipaddressctrl-class"></a>Класс CIPAddressCtrl
Предоставляет функциональные возможности стандартного элемента управления "IP-адрес" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Создает объект `CIPAddressCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|Удаляет содержимое контроль IP-адресов.|  
|[CIPAddressCtrl::Create](#create)|Создает контроль IP-адресов и прикрепляет его к `CIPAddressCtrl` объекта.|  
|[CIPAddressCtrl::CreateEx](#createex)|Создает элемент управления IP-адрес с указанным расширенные стили Windows и прикрепляет его к `CIPAddressCtrl` объекта.|  
|[CIPAddressCtrl::GetAddress](#getaddress)|Извлекает адрес значения для всех четырех полях в контроль IP-адресов.|  
|[CIPAddressCtrl::IsBlank](#isblank)|Определяет, являются ли все поля в контроль IP-адресов пустым.|  
|[CIPAddressCtrl::SetAddress](#setaddress)|Задает адрес значения для всех четырех полях в контроль IP-адресов.|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Задает фокус клавиатуры для указанного поля контроль IP-адресов.|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Задает диапазон в указанном поле в контроль IP-адресов.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления IP-адрес, элемент управления, подобный элемент управления редактированием позволяет вводить и управления ими числовой адрес в формате протокола Интернета (IP).  
  
 Этот элемент управления (и, следовательно, `CIPAddressCtrl` класс) доступен только для программ, запущенных в Microsoft Internet Explorer 4.0 и более поздних версий. Они также будут доступны в будущих версиях Windows и Windows NT.  
  
 Дополнительные общие сведения о контроль IP-адресов см. в разделе [IP адрес управляет](http://msdn.microsoft.com/library/windows/desktop/bb761372) в Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="cipaddressctrl"></a>  CIPAddressCtrl::CIPAddressCtrl  
 Создает объект `CIPAddressCtrl`.  
  
```  
CIPAddressCtrl();
```  
  
##  <a name="clearaddress"></a>  CIPAddressCtrl::ClearAddress  
 Удаляет содержимое контроль IP-адресов.  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377), как описано в Windows SDK.  
  
##  <a name="create"></a>  CIPAddressCtrl::Create  
 Создает контроль IP-адресов и прикрепляет его к `CIPAddressCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Стиль элемента управления IP-адрес. Примените сочетание стилей окна. Необходимо включить **WS_CHILD** стиля, так как элемент управления должен быть дочерним окном. В разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в Windows SDK список стилей windows.  
  
 `rect`  
 Ссылка на размер и положение контроль IP-адресов. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указатель на родительское окно контроль IP-адресов. Он не должен быть **значение NULL.**  
  
 `nID`  
 Идентификатор контроль IP-адресов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CIPAddressCtrl` объекта в два этапа.  
  
1.  Вызывает конструктор, который создает `CIPAddressCtrl` объекта.  
  
2.  Вызовите **создать**, которая создает контроль IP-адресов.  
  
 Если вы хотите использовать с элементом управления windows расширенных стилей, вызовите [CreateEx](#createex) вместо **создать**.  
  
##  <a name="createex"></a>  CIPAddressCtrl::CreateEx  
 Эта функция вызывается для создания элемента управления (дочернего окна) и связать его с `CIPAddressCtrl` объекта.  
  
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
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в Windows SDK.  
  
 `dwStyle`  
 Стиль элемента управления IP-адрес. Примените сочетание стилей окна. Необходимо включить **WS_CHILD** стиля, так как элемент управления должен быть дочерним окном. В разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в Windows SDK список стилей windows.  
  
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
  
##  <a name="getaddress"></a>  CIPAddressCtrl::GetAddress  
 Извлекает адрес значения для всех четырех полях в контроль IP-адресов.  
  
```  
int GetAddress(
    BYTE& nField0,  
    BYTE& nField1,  
    BYTE& nField2,  
    BYTE& nField3);  
  
int GetAddress(DWORD& dwAddress);
```  
  
### <a name="parameters"></a>Параметры  
 `nField0`  
 Ссылка на значение поля 0 упакованный IP-адрес.  
  
 `nField1`  
 Ссылка на значение поля 1 упакованный IP-адрес.  
  
 `nField2`  
 Ссылка на значение поля 2 упакованный IP-адрес.  
  
 `nField3`  
 Ссылка на значение поля 3 упакованный IP-адрес.  
  
 `dwAddress`  
 Ссылка на адрес `DWORD` значение, которое получает IP-адрес. В разделе **примечания** для таблицы, которая показывает, как `dwAddress` заполняется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество непустых полей в контроль IP-адресов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378), как описано в Windows SDK. В первый прототип выше вправо соответственно левый чисел в полях от 0 до 3 элемента управления, чтение, заполнение четыре параметра. В приведенном выше, второй прототипе `dwAddress` заполняется следующим образом.  
  
|Поле|Биты, содержащий значение поля|  
|-----------|-------------------------------------|  
|0|24 до 31|  
|1|16 – 23|  
|2|от 8 до 15|  
|3|от 0 до 7|  
  
##  <a name="isblank"></a>  CIPAddressCtrl::IsBlank  
 Определяет, являются ли все поля в контроль IP-адресов пустым.  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если все поля контроль IP-адресов не пустой. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379), как описано в Windows SDK.  
  
##  <a name="setaddress"></a>  CIPAddressCtrl::SetAddress  
 Задает адрес значения для всех четырех полях в контроль IP-адресов.  
  
```  
void SetAddress(
    BYTE nField0,  
    BYTE nField1,  
    BYTE nField2,  
    BYTE nField3);  
  
void SetAddress(DWORD dwAddress);
```  
  
### <a name="parameters"></a>Параметры  
 `nField0`  
 Значение поля 0 с упакованным IP-адреса.  
  
 `nField1`  
 Значение поля 1 с упакованным IP-адреса.  
  
 `nField2`  
 Значение поля 2 с упакованным IP-адреса.  
  
 `nField3`  
 Значение поля 3 с упакованным IP-адреса.  
  
 `dwAddress`  
 Объект `DWORD` значение, содержащее новый IP-адрес. В разделе **примечания** для таблицы, которая показывает, как `DWORD` указано значение.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380), как описано в Windows SDK. В первый прототип выше вправо соответственно левый чисел в полях от 0 до 3 элемента управления, чтение, заполнение четыре параметра. В приведенном выше, второй прототипе `dwAddress` заполняется следующим образом.  
  
|Поле|Биты, содержащий значение поля|  
|-----------|-------------------------------------|  
|0|24 до 31|  
|1|16 – 23|  
|2|от 8 до 15|  
|3|от 0 до 7|  
  
##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus  
 Задает фокус клавиатуры для указанного поля контроль IP-адресов.  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>Параметры  
 `nField`  
 Индекс (с нуля) поля, к которому должен быть установлен фокус. Если это значение больше, чем количество полей, фокус перемещается в первое пустое поле. Если все поля, отличный от пробела, фокус перемещается к первому полю.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381), как описано в Windows SDK.  
  
##  <a name="setfieldrange"></a>  CIPAddressCtrl::SetFieldRange  
 Задает диапазон в указанном поле в контроль IP-адресов.  
  
```  
void SetFieldRange(
    int nField,  
    BYTE nLower,  
    BYTE nUpper);
```  
  
### <a name="parameters"></a>Параметры  
 `nField`  
 Индекс (с нуля) поля, к которому будет применяться диапазона.  
  
 `nLower`  
 Ссылка на целое число, получение нижнего предела, указанного поля в этом контроль IP-адресов.  
  
 `nUpper`  
 Ссылка на целое число, получение верхний предел для указанного поля в этом контроль IP-адресов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382), как описано в Windows SDK. С помощью двух параметров `nLower` и `nUpper`, чтобы указать нижняя и верхняя границы поля, а не *wRange* параметр, используемый с сообщением Win32.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



