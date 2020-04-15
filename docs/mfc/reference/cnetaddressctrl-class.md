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
ms.openlocfilehash: 71e3b1a9fde84f96696d26c891ab6688f246d575
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363315"
---
# <a name="cnetaddressctrl-class"></a>Класс CNetAddressCtrl

Класс `CNetAddressCtrl` представляет элемент управления сетевого адреса, который можно использовать для ввода и проверки формата IPv4, IPv6 и именованных адресов DNS.

## <a name="syntax"></a>Синтаксис

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Формирует объект `CNetAddressCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CNetAddressCtrl::Создание](#create)|Создает управление сетевым адресом с указанными `CNetAddressCtrl` стилями и прикрепляет его к текущему объекту.|
|[CNetAddressCtrl:CreateEx](#createex)|Создает элемент управления сетевого адреса с указанными `CNetAddressCtrl` расширенными стилями и прикрепляет его к текущему объекту.|
|[CNetAddressCtrl::DisplayОшибкаТип](#displayerrortip)|Отображает наконечник шарика ошибки, когда пользователь вводит неподдерживаемый сетевой адрес в текущем элементе управления адресом сети.|
|[CNetAddressCtrl::GetAddress](#getaddress)|Извлекает проверенное и разображеное представление сетевого адреса, связанного с текущим контролем сетевого адреса.|
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Извлекает тип сетевого адреса, который может поддерживать текущий элемент управления адресом сети.|
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Устанавливает тип сетевого адреса, который может поддерживать текущий элемент управления адресом сети.|

## <a name="remarks"></a>Remarks

Управление сетевого адреса проверяет, что формат адреса, в который вводит пользователь, является правильным. Элемент управления фактически не подключается к сетевому адресу. Метод [CNetAddressCtrl::SetAllowType](#setallowtype) определяет один или несколько типов адресов, которые метод [CNetAddressCtrl::GetAddress](#getaddress) может разобрать и проверить. Адрес может быть в виде IPv4, IPv6 или названного адреса для направления сервера, сети, узла или передачи сообщений. Если формат адреса неправильный, можно использовать метод [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) для отображения ящика с сообщением infotip, который графически указывает на текстовый ящик управления адресом сети и отображает предопределенное сообщение об ошибке.

Класс `CNetAddressCtrl` происходит от класса [CEdit.](../../mfc/reference/cedit-class.md) Следовательно, управление сетевым адресом обеспечивает доступ ко всем сообщениям управления Windows.

Следующая цифра изображает диалог, содержащий элемент управления сетевым адресом. Текстовое окно (1) для управления сетевым адресом содержит недействительный сетевой адрес. Сообщение infotip (2) отображается, если сетевой адрес недействителен.

![Диалог с элементом управления сетевым адресом и подсказкой.](../../mfc/reference/media/cnetaddctrl.png "Диалог с элементом управления сетевым адресом и подсказкой.")

## <a name="example"></a>Пример

Следующий пример кода — это часть диалога, которая проверяет сетевой адрес. Обработчики событий для трех радиокнопок указывают, что сетевой адрес может быть одним из трех типов адресов. Пользователь вводит адрес в текстовом поле управления сетью, а затем нажимает кнопку для проверки адреса. Если адрес действителен, отображается сообщение об успехе; в противном случае отображается предопределенное сообщение об ошибке infotip.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>Пример

Следующий пример кода из файла заголовка диалогов определяет [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) и [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) переменных, требуемых методом [CNetAddressCtrl::GetAddress.](#getaddress)

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

Этот класс поддерживается в Windows Vista и позже.

Дополнительные требования к этому классу описаны в [требованиях к сборке для общих элементов управления Windows Vista.](../../mfc/build-requirements-for-windows-vista-common-controls.md)

## <a name="cnetaddressctrlcnetaddressctrl"></a><a name="cnetaddressctrl"></a>CNetAddressCtrl::CNetAddressCtrl

Формирует объект `CNetAddressCtrl`.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>Remarks

Используйте [CNetAddressCtrl::Создать](#create) или [CNetAddressCtrl::CreateEx](#createex) метод для создания управления `CNetAddressCtrl` сетью и прикрепить его к объекту.

## <a name="cnetaddressctrlcreate"></a><a name="create"></a>CNetAddressCtrl::Создание

Создает управление сетевым адресом с указанными `CNetAddressCtrl` стилями и прикрепляет его к текущему объекту.

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
|*dwStyle*|(в) Битовая комбинация стилей, которые должны быть применены к управлению. Для получения дополнительной информации [см.](../../mfc/reference/styles-used-by-mfc.md#edit-styles)|
|*rect*|(в) Ссылка на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) содержащую положение и размер элемента управления.|
|*pParentWnd*|(в) Не-не-null указатель на [объект CWnd,](../../mfc/reference/cwnd-class.md) который является родительским окном элемента управления.|
|*nID*|(в) Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

## <a name="cnetaddressctrlcreateex"></a><a name="createex"></a>CNetAddressCtrl:CreateEx

Создает элемент управления сетевого адреса с указанными `CNetAddressCtrl` расширенными стилями и прикрепляет его к текущему объекту.

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
|*dwExStyle*|(в) Битовая комбинация (ИЛИ) расширенных стилей, которые должны быть применены к управлению. Для получения дополнительной *dwExStyle* информации см. [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)|
|*dwStyle*|(в) Битовая комбинация (ИЛИ) стилей, которые должны быть применены к управлению. Для получения дополнительной информации [см.](../../mfc/reference/styles-used-by-mfc.md#edit-styles)|
|*rect*|(в) Ссылка на структуру [RECT,](/previous-versions/dd162897\(v=vs.85\)) содержащую положение и размер элемента управления.|
|*pParentWnd*|(в) Не-не-null указатель на [объект CWnd,](../../mfc/reference/cwnd-class.md) который является родительским окном элемента управления.|
|*nID*|(в) Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE.

## <a name="cnetaddressctrldisplayerrortip"></a><a name="displayerrortip"></a>CNetAddressCtrl::DisplayОшибкаТип

Отображает сообщение об ошибке в наконечнике шарика, связанном с текущим управлением адресом сети.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, `S_OK` если этот метод является успешным; в противном случае код ошибки.

### <a name="remarks"></a>Remarks

Используйте метод [CNetAddressCtrl::SetAllowType](#setallowtype) для указания типов адресов, которые может поддерживать текущий контроль сетевого адреса. Используйте метод [CNetAddressCtrl::GetAddress](#getaddress) для проверки и разбора сетевого адреса, в который вводит пользователь. Используйте метод [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) для отображения инфотипа сообщения об ошибке, если метод [CNetAddressCtrl::GetAddress](#getaddress) метод не работает.

Это сообщение ссылается на [NetAddr_DisplayErrorTip](/windows/win32/api/shellapi/nf-shellapi-netaddr_displayerrortip) макрос, который описан в Windows SDK. Этот макрос `NCM_DISPLAYERRORTIP` посылает сообщение.

## <a name="cnetaddressctrlgetaddress"></a><a name="getaddress"></a>CNetAddressCtrl::GetAddress

Извлекает проверенное и разображеное представление сетевого адреса, связанное с текущим контролем сетевого адреса.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>Параметры

*pAddress*<br/>
(в, вне) Указатель на [NC_ADDRESS](/windows/win32/api/shellapi/ns-shellapi-nc_address) структуру.  Перед вызовом метода GetAddress установите член участи этой структуры *pAddrInfo* на адрес [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) структуры.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если этот метод является успешным; в противном случае код ошибки COM. Для получения дополнительной информации о возможных кодах ошибок с [NetAddr_GetAddressм.](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress)

### <a name="remarks"></a>Remarks

Если этот метод успешен, структура [NET_ADDRESS_INFO](/windows/win32/shell/hkey-type) содержит дополнительную информацию о сетевом адресе.

Используйте метод [CNetAddressCtrl::SetAllowType](#setallowtype) для указания типов адресов текущего сетевого адреса, который может поддерживаться. Используйте метод [CNetAddressCtrl::GetAddress](#getaddress) для проверки и разбора сетевого адреса, в который вводит пользователь. Используйте метод [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) для отображения инфотипа сообщения об ошибке, если метод [CNetAddressCtrl::GetAddress](#getaddress) метод не работает.

Этот метод вызывает [NetAddr_GetAddress](/windows/win32/api/shellapi/nf-shellapi-netaddr_getaddress) макрос, который описан в SDK Windows. Этот макрос посылает NCM_GETADDRESS сообщение.

## <a name="cnetaddressctrlgetallowtype"></a><a name="getallowtype"></a>CNetAddressCtrl::GetAllowType

Извлекает тип сетевого адреса, который может поддерживать текущий элемент управления адресом сети.

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Битовая комбинация (ИЛИ) флагов, которая определяет типы адресов управления сетевым адресом, могут поддерживаться. Для получения дополнительной информации [NET_STRING](/windows/win32/shell/net-string)см.

### <a name="remarks"></a>Remarks

Это сообщение ссылается на [NetAddr_GetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_getallowtype) макрос, который описан в Windows SDK. Этот макрос посылает NCM_GETALLOWTYPE сообщение.

## <a name="cnetaddressctrlsetallowtype"></a><a name="setallowtype"></a>CNetAddressCtrl::SetAllowType

Устанавливает тип сетевого адреса, который может поддерживать текущий элемент управления адресом сети.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*dwAddrMask*|(в) Битовая комбинация (ИЛИ) флагов, которая определяет типы адресов управления сетевым адресом, могут поддерживаться. Для получения дополнительной информации [NET_STRING](/windows/win32/shell/net-string)см.|

### <a name="return-value"></a>Возвращаемое значение

S_OK, если этот метод является успешным; в противном случае код ошибки COM.

### <a name="remarks"></a>Remarks

Используйте метод [CNetAddressCtrl::SetAllowType](#setallowtype) для указания типов адресов, которые может поддерживать текущий контроль сетевого адреса. Используйте метод [CNetAddressCtrl::GetAddress](#getaddress) для проверки и разбора сетевого адреса, в который вводит пользователь. Используйте метод [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) для отображения инфотипа сообщения об ошибке, если метод [CNetAddressCtrl::GetAddress](#getaddress) метод не работает.

Это сообщение ссылается на [NetAddr_SetAllowType](/windows/win32/api/shellapi/nf-shellapi-netaddr_setallowtype) макрос, который описан в Windows SDK. Этот макрос посылает NCM_SETALLOWTYPE сообщение.

## <a name="see-also"></a>См. также раздел

[Класс CNetAddressCtrl](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)
