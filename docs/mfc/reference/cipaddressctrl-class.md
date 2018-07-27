---
title: Класс CIPAddressCtrl | Документация Майкрософт
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
ms.openlocfilehash: b6c7d45c36534ab2c67765dc6e4e9ea61b79b3ea
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338036"
---
# <a name="cipaddressctrl-class"></a>Класс CIPAddressCtrl
Предоставляет функциональные возможности стандартного элемента управления "IP-адрес" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Создает объект `CIPAddressCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|Очищает содержимое контроль IP-адресов.|  
|[CIPAddressCtrl::Create](#create)|Создает элемент управления адрес IP-адрес и присоединяет его к `CIPAddressCtrl` объекта.|  
|[CIPAddressCtrl::CreateEx](#createex)|Создает элемент управления IP-адрес с указанным расширенные стили Windows и присоединяет его к `CIPAddressCtrl` объекта.|  
|[CIPAddressCtrl::GetAddress](#getaddress)|Извлекает адрес значения для всех четырех полей в контроль IP-адресов.|  
|[CIPAddressCtrl::IsBlank](#isblank)|Определяет, если все поля в контроль IP-адресов являются пустыми.|  
|[CIPAddressCtrl::SetAddress](#setaddress)|Задает адрес значения для всех четырех полей в контроль IP-адресов.|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Устанавливает фокус клавиатуры для указанного поля в контроль IP-адресов.|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Задает диапазон в указанном поле в контроль IP-адресов.|  
  
## <a name="remarks"></a>Примечания  
 Элемент управления IP-адрес, элемент управления аналогично элемент управления редактирования, позволяет ввести и манипулировать числовой адрес в формате протокола Интернета (IP).  
  
 Этот элемент управления (и, следовательно `CIPAddressCtrl` класс) доступен только для программ, работающих в Microsoft Internet Explorer 4.0 и более поздних версий. Они также будут доступны в будущих версиях Windows и Windows NT.  
  
 Более общие сведения о контроль IP-адресов, см. в разделе [IP адрес управляет](http://msdn.microsoft.com/library/windows/desktop/bb761372) в пакете Windows SDK.  
  
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
 Очищает содержимое контроль IP-адресов.  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377), как описано в пакете Windows SDK.  
  
##  <a name="create"></a>  CIPAddressCtrl::Create  
 Создает элемент управления адрес IP-адрес и присоединяет его к `CIPAddressCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *dwStyle*  
 Стиль элемента управления IP-адрес. Примените сочетание стилей окна. Стиль WS_CHILD необходимо включить, так как элемент управления должен быть дочернего окна. См. в разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в пакете SDK Windows для получения списка стили windows.  
  
 *Rect*  
 Ссылка на размер и положение контроль IP-адресов. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 *pParentWnd*  
 Указатель на родительское окно контроль IP-адресов. Он не должен иметь значение NULL.  
  
 *nID*  
 Идентификатор контроль IP-адресов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 При создании `CIPAddressCtrl` объекта в два этапа.  
  
1.  Вызвать конструктор, который создает `CIPAddressCtrl` объекта.  
  
2.  Вызовите `Create`, который создает контроль IP-адресов.  
  
 Если вы хотите использовать windows расширенных стилей с элементом управления, вызовите [CreateEx](#createex) вместо `Create`.  
  
##  <a name="createex"></a>  CIPAddressCtrl::CreateEx  
 Вызывайте эту функцию для создания элемента управления (дочернего окна) и свяжите ее с `CIPAddressCtrl` объекта.  
  
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
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в пакете Windows SDK.  
  
 *dwStyle*  
 Стиль элемента управления IP-адрес. Примените сочетание стилей окна. Стиль WS_CHILD необходимо включить, так как элемент управления должен быть дочернего окна. См. в разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в пакете SDK Windows для получения списка стили windows.  
  
 *Rect*  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.  
  
 *pParentWnd*  
 Указатель на окно, которое является родительским для элемента управления.  
  
 *nID*  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.  
  
##  <a name="getaddress"></a>  CIPAddressCtrl::GetAddress  
 Извлекает адрес значения для всех четырех полей в контроль IP-адресов.  
  
```  
int GetAddress(
    BYTE& nField0,  
    BYTE& nField1,  
    BYTE& nField2,  
    BYTE& nField3);  
  
int GetAddress(DWORD& dwAddress);
```  
  
### <a name="parameters"></a>Параметры  
 *nField0*  
 Ссылка на значение поля 0 с упакованным IP-адреса.  
  
 *nField1*  
 Ссылка на значение поля 1 с упакованным IP-адреса.  
  
 *nField2*  
 Ссылка на значение поля 2 с упакованным IP-адреса.  
  
 *nField3*  
 Ссылка на значение поля 3 с упакованным IP-адреса.  
  
 *dwAddress*  
 Ссылка на адрес значения DWORD, которое получает IP-адрес. См. в разделе **"Примечания"** в таблице, показано, как *dwAddress* заполняется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество непустых полей в контроль IP-адресов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378), как описано в пакете Windows SDK. В первый прототип выше прямо соответственно остается чисел в полях от 0 до 3 элемента управления, чтение, заполнение четыре параметра. В приведенном выше, второй прототипе *dwAddress* заполняется следующим образом.  
  
|Поле|Биты, содержащий значение поля|  
|-----------|-------------------------------------|  
|0|24 до 31|  
|1|16 до 23|  
|2|8 – 15|  
|3|от 0 до 7|  
  
##  <a name="isblank"></a>  CIPAddressCtrl::IsBlank  
 Определяет, если все поля в контроль IP-адресов являются пустыми.  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если все поля контроль IP-адресов являются пустыми; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379), как описано в пакете Windows SDK.  
  
##  <a name="setaddress"></a>  CIPAddressCtrl::SetAddress  
 Задает адрес значения для всех четырех полей в контроль IP-адресов.  
  
```  
void SetAddress(
    BYTE nField0,  
    BYTE nField1,  
    BYTE nField2,  
    BYTE nField3);  
  
void SetAddress(DWORD dwAddress);
```  
  
### <a name="parameters"></a>Параметры  
 *nField0*  
 Значение поля 0 с упакованным IP-адреса.  
  
 *nField1*  
 Значение поля 1 с упакованным IP-адреса.  
  
 *nField2*  
 Значение поля 2 с упакованным IP-адреса.  
  
 *nField3*  
 Значение поля 3 с упакованным IP-адреса.  
  
 *dwAddress*  
 Значение DWORD, содержащее новый IP-адрес. См. в разделе **"Примечания"** для таблицы, которая показывает, как указано значение DWORD.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380), как описано в пакете Windows SDK. В первый прототип выше прямо соответственно остается чисел в полях от 0 до 3 элемента управления, чтение, заполнение четыре параметра. В приведенном выше, второй прототипе *dwAddress* заполняется следующим образом.  
  
|Поле|Биты, содержащий значение поля|  
|-----------|-------------------------------------|  
|0|24 до 31|  
|1|16 до 23|  
|2|8 – 15|  
|3|от 0 до 7|  
  
##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus  
 Устанавливает фокус клавиатуры для указанного поля в контроль IP-адресов.  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>Параметры  
 *nField*  
 Индекс (с нуля) поля, к которому должен быть установлен фокус. Если это значение превышает число полей, фокус перемещается в первое пустое поле. Если все поля, отличный от пробела, фокус перемещается в первое поле.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381), как описано в пакете Windows SDK.  
  
##  <a name="setfieldrange"></a>  CIPAddressCtrl::SetFieldRange  
 Задает диапазон в указанном поле в контроль IP-адресов.  
  
```  
void SetFieldRange(
    int nField,  
    BYTE nLower,  
    BYTE nUpper);
```  
  
### <a name="parameters"></a>Параметры  
 *nField*  
 Индекс (с нуля) поля, к которому будет применяться диапазона.  
  
 *nLower*  
 Ссылка на целое число, получение нижний предел для указанного поля в этом контроль IP-адресов.  
  
 *nUpper*  
 Ссылка на целое число, получение верхнее предельное значение указанного поля в этом контроль IP-адресов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщение Win32 [IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382), как описано в пакете Windows SDK. С помощью двух параметров, *nLower* и *nUpper*, чтобы указать, нижний и верхний пределы поля, а не *wRange* параметр, используемый с сообщением Win32.  
  
## <a name="see-also"></a>См. также  
 [Класс CWnd](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



