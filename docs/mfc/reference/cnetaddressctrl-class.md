---
title: Класс CNetAddressCtrl
ms.date: 11/19/2018
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
ms.openlocfilehash: 5e485c22bcc4bf35f61226d84345102052689f89
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "69504538"
---
# <a name="cnetaddressctrl-class"></a>Класс CNetAddressCtrl

Класс `CNetAddressCtrl` представляет элемент управления сетевого адреса, который можно использовать для ввода и проверки формата IPv4, IPv6 и именованных адресов DNS.

## <a name="syntax"></a>Синтаксис

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CNetAddressCtrl:: CNetAddressCtrl](#cnetaddressctrl)|Создает объект `CNetAddressCtrl`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CNetAddressCtrl:: Create](#create)|Создает элемент управления "сетевой адрес" с указанными стилями и прикрепляет `CNetAddressCtrl` его к текущему объекту.|
|[CNetAddressCtrl:: Креатикс](#createex)|Создает элемент управления "сетевой адрес" с указанными расширенными стилями и прикрепляет его к текущему `CNetAddressCtrl` объекту.|
|[CNetAddressCtrl::D Исплайеррортип](#displayerrortip)|Отображает всплывающую подсказку об ошибке, когда пользователь вводит неподдерживаемый сетевой адрес в текущий элемент управления "сетевой адрес".|
|[CNetAddressCtrl:: наадресовать](#getaddress)|Извлекает проверенное и Проанализированное представление сетевого адреса, связанного с текущим элементом управления сетевыми адресами.|
|[CNetAddressCtrl:: Жеталловтипе](#getallowtype)|Возвращает тип сетевого адреса, который может поддерживать текущий элемент управления "Сетевая адресация".|
|[CNetAddressCtrl:: Сеталловтипе](#setallowtype)|Задает тип сетевого адреса, который может поддерживать текущий элемент управления сетью.|

## <a name="remarks"></a>Примечания

Элемент управления "сетевой адрес" проверяет правильность формата адреса, вводимого пользователем. Элемент управления фактически не подключается к сетевому адресу. Метод [CNetAddressCtrl:: сеталловтипе](#setallowtype) указывает один или несколько типов адресов, которые могут проанализировать и проверить метод [CNetAddressCtrl::](#getaddress) . Адрес может быть в формате IPv4, IPv6 или именованного адреса для сервера, сети, узла или назначения широковещательного сообщения. Если формат адреса неверен, можно использовать метод [CNetAddressCtrl::D исплайеррортип](#displayerrortip) для отображения окна сообщения подсказки, которое графически указывает на текстовое поле элемента управления "сетевые адреса", и отображает предопределенное сообщение об ошибке.

Класс является производным от класса [CEdit.](../../mfc/reference/cedit-class.md) `CNetAddressCtrl` Следовательно, элемент управления "сетевой адрес" предоставляет доступ ко всем сообщениям управления Windows Edit.

На следующем рисунке показано диалоговое окно, содержащее элемент управления "сетевой адрес". Текстовое поле (1) для элемента управления "сетевые адреса" содержит недопустимый сетевой адрес. Сообщение подсказки (2) отображается, если сетевой адрес является недопустимым.

![Диалоговое окно с элементом управления сетевыми адресами и подсказкой.](../../mfc/reference/media/cnetaddctrl.png "Диалоговое окно с элементом управления сетевыми адресами и подсказкой.")

## <a name="example"></a>Пример

Следующий пример кода является частью диалогового окна, который проверяет сетевой адрес. Обработчики событий для трех переключателей указывают, что сетевой адрес может быть одним из трех типов адресов. Пользователь вводит адрес в текстовое поле элемента управления сетью, а затем нажимает кнопку для проверки адреса. Если адрес является допустимым, отображается сообщение об успешном выполнении. в противном случае отображается предопределенное сообщение об ошибке всплывающей подсказки.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>Пример

В следующем примере кода из файла заголовка диалогового окна определяются переменные [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) и [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) , необходимые для метода [CNetAddressCtrl::](#getaddress) Method.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

Этот класс поддерживается в Windows Vista и более поздних версиях.

Дополнительные требования для этого класса описаны в статье [требования к сборке для стандартных элементов управления Windows Vista](../../mfc/build-requirements-for-windows-vista-common-controls.md).

##  <a name="cnetaddressctrl"></a>CNetAddressCtrl:: CNetAddressCtrl

Создает объект `CNetAddressCtrl`.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>Примечания

Используйте метод [CNetAddressCtrl:: Create](#create) или [CNetAddressCtrl:: креатикс](#createex) , чтобы создать сетевой элемент управления и присоединить `CNetAddressCtrl` его к объекту.

##  <a name="create"></a>CNetAddressCtrl:: Create

Создает элемент управления "сетевой адрес" с указанными стилями и прикрепляет `CNetAddressCtrl` его к текущему объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*двстиле*|окне Битовая комбинация стилей, применяемых к элементу управления. Дополнительные сведения см. в разделе [Edit Styles](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*rect*|окне Ссылка на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , которая содержит расположение и размер элемента управления.|
|*ппарентвнд*|окне Указатель, отличный от NULL, на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является родительским окном элемента управления.|
|*nID*|окне Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

##  <a name="createex"></a>CNetAddressCtrl:: Креатикс

Создает элемент управления "сетевой адрес" с указанными расширенными стилями и прикрепляет его к текущему `CNetAddressCtrl` объекту.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*двексстиле*|окне Побитовое сочетание (или) расширенных стилей, применяемых к элементу управления. Дополнительные сведения см. в описании параметра *двексстиле* функции [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) .|
|*двстиле*|окне Побитовое сочетание (или) стилей, применяемых к элементу управления. Дополнительные сведения см. в разделе [Edit Styles](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*rect*|окне Ссылка на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , которая содержит расположение и размер элемента управления.|
|*ппарентвнд*|окне Указатель, отличный от NULL, на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является родительским окном элемента управления.|
|*nID*|окне Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

##  <a name="displayerrortip"></a>CNetAddressCtrl::D Исплайеррортип

Отображает сообщение об ошибке в подсказке, связанной с текущим элементом управления сетевыми адресами.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>Возвращаемое значение

Значение `S_OK` , если этот метод выполнен успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

Используйте метод [CNetAddressCtrl:: сеталловтипе](#setallowtype) , чтобы указать типы адресов, которые может поддерживать текущий элемент управления сетевого адреса. Используйте метод [CNetAddressCtrl::](#getaddress) Method для проверки и анализа сетевого адреса, вводимого пользователем. Используйте метод [CNetAddressCtrl::D исплайеррортип](#displayerrortip) , чтобы отобразить всплывающую подсказку сообщения об ошибке, если метод [CNetAddressCtrl::-Address](#getaddress) завершился неудачно.

Это сообщение вызывает макрос [NetAddr_DisplayErrorTip](/windows/win32/api/shellapi/nf-shellapi-netaddr_displayerrortip) , описанный в Windows SDK. Этот макрос отправляет `NCM_DISPLAYERRORTIP` сообщение.

##  <a name="getaddress"></a>CNetAddressCtrl:: наадресовать

Извлекает проверенное и Проанализированное представление сетевого адреса, связанного с текущим элементом управления сетевыми адресами.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>Параметры

*паддресс*<br/>
[вход, выход] Указатель на структуру [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) .  Задайте для элемента *паддринфо* этой структуры адрес структуры [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) , прежде чем вызывать метод метода WebMethod.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если этот метод успешно выполнен; в противном случае — код ошибки COM. Дополнительные сведения о возможных кодах ошибок см. в разделе возвращаемое значение макроса [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) .

### <a name="remarks"></a>Примечания

Если этот метод успешно выполнен, структура [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) содержит дополнительные сведения о сетевом адресе.

Используйте метод [CNetAddressCtrl:: сеталловтипе](#setallowtype) , чтобы указать типы адресов, которые может поддерживать текущий элемент управления сетевого адреса. Используйте метод [CNetAddressCtrl::](#getaddress) Method для проверки и анализа сетевого адреса, вводимого пользователем. Используйте метод [CNetAddressCtrl::D исплайеррортип](#displayerrortip) , чтобы отобразить всплывающую подсказку сообщения об ошибке, если метод [CNetAddressCtrl::-Address](#getaddress) завершился неудачно.

Этот метод вызывает макрос [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) , описанный в Windows SDK. Этот макрос отправляет сообщение NCM_GETADDRESS.

##  <a name="getallowtype"></a>CNetAddressCtrl:: Жеталловтипе

Возвращает тип сетевого адреса, который может поддерживать текущий элемент управления "Сетевая адресация".

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Побитовое сочетание (или) флагов, указывающих типы адресов, которые может поддерживать элемент управления "сетевой адрес". Дополнительные сведения см. в разделе [NET_STRING](/windows/win32/shell/net-string).

### <a name="remarks"></a>Примечания

Это сообщение вызывает макрос [NetAddr_GetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_getallowtype) , описанный в Windows SDK. Этот макрос отправляет сообщение NCM_GETALLOWTYPE.

##  <a name="setallowtype"></a>CNetAddressCtrl:: Сеталловтипе

Задает тип сетевого адреса, который может поддерживать текущий элемент управления сетью.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*дваддрмаск*|окне Побитовое сочетание (или) флагов, указывающих типы адресов, которые может поддерживать элемент управления "сетевой адрес". Дополнительные сведения см. в разделе [NET_STRING](/windows/win32/shell/net-string).|

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если этот метод успешно выполнен; в противном случае — код ошибки COM.

### <a name="remarks"></a>Примечания

Используйте метод [CNetAddressCtrl:: сеталловтипе](#setallowtype) , чтобы указать типы адресов, которые может поддерживать текущий элемент управления сетевого адреса. Используйте метод [CNetAddressCtrl::](#getaddress) Method для проверки и анализа сетевого адреса, вводимого пользователем. Используйте метод [CNetAddressCtrl::D исплайеррортип](#displayerrortip) , чтобы отобразить всплывающую подсказку сообщения об ошибке, если метод [CNetAddressCtrl::-Address](#getaddress) завершился неудачно.

Это сообщение вызывает макрос [NetAddr_SetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_setallowtype) , описанный в Windows SDK. Этот макрос отправляет сообщение NCM_SETALLOWTYPE.

## <a name="see-also"></a>См. также

[Класс CNetAddressCtrl](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)
