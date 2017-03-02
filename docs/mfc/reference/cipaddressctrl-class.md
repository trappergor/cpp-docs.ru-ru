---
title: "Класс CIPAddressCtrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CIPAddressCtrl
dev_langs:
- C++
helpviewer_keywords:
- IP address control
- Internet address edit box
- CIPAddressCtrl class
- Internet protocol address box
- common controls, Internet Explorer 4.0
- Internet Explorer 4.0 common controls
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
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
ms.openlocfilehash: b3849580c7bfd07f241e55cc48144959566d7d09
ms.lasthandoff: 02/24/2017

---
# <a name="cipaddressctrl-class"></a>Класс CIPAddressCtrl
Предоставляет функциональные возможности стандартного элемента управления "IP-адрес" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Создает объект `CIPAddressCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|Удаляет содержимое контроль IP-адресов.|  
|[CIPAddressCtrl::Create](#create)|Контроль IP-адресов создает и присоединяет его к `CIPAddressCtrl` объекта.|  
|[CIPAddressCtrl::CreateEx](#createex)|Создает элемент управления IP-адреса с указанным расширенные стили Windows и присоединяет его к `CIPAddressCtrl` объекта.|  
|[CIPAddressCtrl::GetAddress](#getaddress)|Извлекает адрес значения для всех четырех полей в контроль IP-адресов.|  
|[CIPAddressCtrl::IsBlank](#isblank)|Определяет, будут ли пустые все поля в контроль IP-адресов.|  
|[CIPAddressCtrl::SetAddress](#setaddress)|Задает адрес значения для всех четырех полях в контроль IP-адресов.|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Задает фокус клавиатуры для указанного поля в контроль IP-адресов.|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Задает диапазон в указанном поле в контроль IP-адресов.|  
  
## <a name="remarks"></a>Примечания  
 IP-адрес управления, аналогично элемент управления, позволяет вводить и управлять числовой адрес в формате протокола Интернета (IP).  
  
 Этот элемент управления (и, следовательно, `CIPAddressCtrl` класса) доступен только для программ, запущенных в Microsoft Internet Explorer 4.0 и более поздних версий. Они также будут доступны в будущих версиях Windows и Windows NT.  
  
 Более общие сведения о контроль IP-адресов см. в разделе [IP адрес управляет](http://msdn.microsoft.com/library/windows/desktop/bb761372) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-namecipaddressctrla--cipaddressctrlcipaddressctrl"></a><a name="cipaddressctrl"></a>CIPAddressCtrl::CIPAddressCtrl  
 Создает объект `CIPAddressCtrl`.  
  
```  
CIPAddressCtrl();
```  
  
##  <a name="a-nameclearaddressa--cipaddressctrlclearaddress"></a><a name="clearaddress"></a>CIPAddressCtrl::ClearAddress  
 Удаляет содержимое контроль IP-адресов.  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecreatea--cipaddressctrlcreate"></a><a name="create"></a>CIPAddressCtrl::Create  
 Контроль IP-адресов создает и присоединяет его к `CIPAddressCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Стиль элемента управления IP-адрес. Примените сочетание стили окна. Необходимо включить **WS_CHILD** стиля, так как элемент управления должен быть дочернего окна. В разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список стилей windows.  
  
 `rect`  
 Ссылка на размер и положение контроль IP-адресов. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры.  
  
 `pParentWnd`  
 Указатель на родительское окно контроль IP-адресов. Оно не должно быть **значение NULL.**  
  
 `nID`  
 Идентификатор контроль IP-адресов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CIPAddressCtrl` объекта в два этапа.  
  
1.  Вызовите конструктор, который создает `CIPAddressCtrl` объекта.  
  
2.  Вызов **создать**, который создает контроль IP-адресов.  
  
 Если вы хотите использовать с элементом управления windows расширенные стили, вызвать [CreateEx](#createex) вместо **создать**.  
  
##  <a name="a-namecreateexa--cipaddressctrlcreateex"></a><a name="createex"></a>CIPAddressCtrl::CreateEx  
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
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Стиль элемента управления IP-адрес. Примените сочетание стили окна. Необходимо включить **WS_CHILD** стиля, так как элемент управления должен быть дочернего окна. В разделе [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] список стилей windows.  
  
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
  
##  <a name="a-namegetaddressa--cipaddressctrlgetaddress"></a><a name="getaddress"></a>CIPAddressCtrl::GetAddress  
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
 `nField0`  
 Ссылка на значение поля 0 упакованным IP-адрес.  
  
 `nField1`  
 Ссылка на значение поля 1 упакованным IP-адрес.  
  
 `nField2`  
 Ссылка на значение поля 2 упакованным IP-адрес.  
  
 `nField3`  
 Ссылка на значение поля 3 упакованным IP-адрес.  
  
 `dwAddress`  
 Ссылка на адрес `DWORD` значение, которое получает IP-адрес. В разделе **примечания** для таблицы, показано, как `dwAddress` заполняется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество непустых полей в контроль IP-адресов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В первый прототип выше числа от 0 до 3 элемента управления, поля чтения слева вправо соответственно, заполнение четыре параметра. В прототипе второй выше `dwAddress` заполняется следующим образом.  
  
|Поле|Биты, содержащий значение поля|  
|-----------|-------------------------------------|  
|0|24 до 31|  
|1|16 до 23|  
|2|от 8 до 15|  
|3|от 0 до 7|  
  
##  <a name="a-nameisblanka--cipaddressctrlisblank"></a><a name="isblank"></a>CIPAddressCtrl::IsBlank  
 Определяет, будут ли пустые все поля в контроль IP-адресов.  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если все поля контроль IP-адресов пустой. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetaddressa--cipaddressctrlsetaddress"></a><a name="setaddress"></a>CIPAddressCtrl::SetAddress  
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
 A `DWORD` значение, содержащее новый IP-адрес. В разделе **примечания** для таблицы, показано, как `DWORD` значение заполняется.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. В первый прототип выше числа от 0 до 3 элемента управления, поля чтения слева вправо соответственно, заполнение четыре параметра. В прототипе второй выше `dwAddress` заполняется следующим образом.  
  
|Поле|Биты, содержащий значение поля|  
|-----------|-------------------------------------|  
|0|24 до 31|  
|1|16 до 23|  
|2|от 8 до 15|  
|3|от 0 до 7|  
  
##  <a name="a-namesetfieldfocusa--cipaddressctrlsetfieldfocus"></a><a name="setfieldfocus"></a>CIPAddressCtrl::SetFieldFocus  
 Задает фокус клавиатуры для указанного поля в контроль IP-адресов.  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>Параметры  
 `nField`  
 Индекс (с нуля) поля, к которому должен быть установлен фокус. Если это значение больше, чем количество полей, фокус перемещается в первое пустое поле. Если все поля, отличный от пробела, фокус перемещается к первому полю.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetfieldrangea--cipaddressctrlsetfieldrange"></a><a name="setfieldrange"></a>CIPAddressCtrl::SetFieldRange  
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
 Ссылка на целое число, получение нижний предел для указанного поля в этом контроль IP-адресов.  
  
 `nUpper`  
 Ссылка на целое число, получение верхнее предельное значение указанного поля в этом контроль IP-адресов.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. С помощью двух параметров `nLower` и `nUpper`, чтобы указать, нижний и верхний пределы поля, а не *wRange* параметр, используемый с сообщением Win32.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




