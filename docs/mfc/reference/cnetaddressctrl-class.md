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
ms.openlocfilehash: ee44c05fa6417aaca367798d7a94a900d521b896
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176242"
---
# <a name="cnetaddressctrl-class"></a>Класс CNetAddressCtrl

Класс `CNetAddressCtrl` представляет элемент управления сетевого адреса, который можно использовать для ввода и проверки формата IPv4, IPv6 и именованных адресов DNS.

## <a name="syntax"></a>Синтаксис

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Создает объект `CNetAddressCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CNetAddressCtrl::Create](#create)|Создает элемент управления network address с указанными стилями и присоединяет его к текущему `CNetAddressCtrl` объекта.|
|[CNetAddressCtrl::CreateEx](#createex)|Создает элемент управления network address с указанным расширенные стили и присоединяет его к текущему `CNetAddressCtrl` объекта.|
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Отображает ошибке всплывающую подсказку, когда пользователь вводит адрес сети не поддерживается в текущий элемент управления network address.|
|[CNetAddressCtrl::GetAddress](#getaddress)|Извлекает проверенные и проанализированное представление сетевой адрес, связанный с текущей управления сетевым адресом.|
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Получает тип сетевой адрес, который может поддерживать текущий элемент управления network address.|
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Задает тип сетевой адрес, который может поддерживать текущий элемент управления network address.|

## <a name="remarks"></a>Примечания

Элемент управления network address проверяет правильность формат адреса, что вводит пользователь. Элемент управления не фактически подключиться к сетевой адрес. [CNetAddressCtrl::SetAllowType](#setallowtype) метод задает один или несколько типов адреса, [CNetAddressCtrl::GetAddress](#getaddress) метод можно проанализировать и проверить. Адрес может быть в формате IPv4, IPv6, или с указанным адресом для сервера, сети, узла или назначение широковещательных сообщений. Если имеет неправильный формат адреса, можно использовать [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод, чтобы отобразить окно сообщения подсказку графически в текстовое поле элемент управления network address и отображает предопределенный сообщение об ошибке.

`CNetAddressCtrl` Класс является производным от [CEdit](../../mfc/reference/cedit-class.md) класса. Следовательно элемент управления network address предоставляет доступ ко всем сообщениям, элемент управления редактирования Windows.

На следующем рисунке представлен диалог, содержащий элемент управления network address. Текстовое поле (1) для управления сетевым адресом содержит недопустимый сетевой адрес. (2) сообщения всплывающая подсказка отображается в том случае, если сетевой адрес является недопустимым.

![Диалоговое окно с элементом управления сетевым адресом и подсказкой. ](../../mfc/reference/media/cnetaddctrl.png "Диалоговое окно с элементом управления сетевым адресом и подсказкой.")

## <a name="example"></a>Пример

В следующем примере кода приведен фрагмент диалогового окна проверки сетевого адреса. Обработчики событий для трех переключателей укажите, что сетевой адрес может принимать одно из трех типов адрес. Пользователь вводит адрес в текстовом поле элемента управления сети, а затем нажимает кнопку для проверки адреса. Если адрес является допустимым, отображается сообщение об успешном выполнении; в противном случае отображается сообщение об ошибке предопределенные подсказку.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>Пример

В следующем примере кода из файла заголовка диалогового окна определяется [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address) и [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) переменные, которые требуются [CNetAddressCtrl::GetAddress](#getaddress)метод.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

Этот класс поддерживается в Windows Vista и более поздних версий.

Дополнительные требования для данного класса описаны в [построения требования для Windows Vista стандартные элементы управления](../../mfc/build-requirements-for-windows-vista-common-controls.md).

##  <a name="cnetaddressctrl"></a>  CNetAddressCtrl::CNetAddressCtrl

Создает объект `CNetAddressCtrl`.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>Примечания

Используйте [CNetAddressCtrl::Create](#create) или [CNetAddressCtrl::CreateEx](#createex) метод для создания элемента управления сети и подключить его к `CNetAddressCtrl` объекта.

##  <a name="create"></a>  CNetAddressCtrl::Create

Создает элемент управления network address с указанными стилями и присоединяет его к текущему `CNetAddressCtrl` объекта.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*dwStyle*|[in] Побитовое сочетание стили элемента управления к элементу управления. Дополнительные сведения см. в разделе [изменить стили](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*rect*|[in] Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления.|
|*pParentWnd*|[in] Ненулевой указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, являющийся родительского окна элемента управления.|
|*nID*|[in] Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

##  <a name="createex"></a>  CNetAddressCtrl::CreateEx

Создает элемент управления network address с указанным расширенные стили и присоединяет его к текущему `CNetAddressCtrl` объекта.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*dwExStyle*|[in] Побитовое сочетание (OR) расширенные стили для применения к элементу управления. Дополнительные сведения см. в разделе *dwExStyle* параметр [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) функции.|
|*dwStyle*|[in] Побитовое сочетание (OR) стили элемента управления к элементу управления. Дополнительные сведения см. в разделе [изменить стили](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*rect*|[in] Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, содержащая положение и размер элемента управления.|
|*pParentWnd*|[in] Ненулевой указатель на [CWnd](../../mfc/reference/cwnd-class.md) объект, являющийся родительского окна элемента управления.|
|*nID*|[in] Идентификатор элемента управления.|

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — значение FALSE.

##  <a name="displayerrortip"></a>  CNetAddressCtrl::DisplayErrorTip

Отображает сообщение об ошибке в всплывающую подсказку, которая связана с текущего управления сетевым адресом.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>Возвращаемое значение

Значение `S_OK` Если этот метод выполнен успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

Используйте [CNetAddressCtrl::SetAllowType](#setallowtype) метод, чтобы указать типы адресов, которые может поддерживать текущего управления сетевым адресом. Используйте [CNetAddressCtrl::GetAddress](#getaddress) метод для проверки и проанализировать сетевой адрес, вводимых пользователем. Используйте [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод для отображения сообщения ошибке всплывающую подсказку, если [CNetAddressCtrl::GetAddress](#getaddress) метод завершается неудачно.

Это сообщение вызывает [NetAddr_DisplayErrorTip](/windows/desktop/api/shellapi/nf-shellapi-netaddr_displayerrortip) макрос, который описан в пакете Windows SDK. Этот макрос отправляет `NCM_DISPLAYERRORTIP` сообщения.

##  <a name="getaddress"></a>  CNetAddressCtrl::GetAddress

Извлекает проверенные и проанализированное представление сетевой адрес, связанный с текущей управления сетевым адресом.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>Параметры

*pAddress*<br/>
[in, out] Указатель на [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address) структуры.  Задайте *pAddrInfo* член этой структуры в адрес [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) структуры перед вызовом метода GetAddress.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если этот метод выполнен успешно; в противном случае — код ошибки COM. Дополнительные сведения о кодах возможных ошибок см. в разделе разделе возвращают значение [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress) макрос.

### <a name="remarks"></a>Примечания

При успешном выполнении, этот метод [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) структура содержит дополнительные сведения о сетевой адрес.

Используйте [CNetAddressCtrl::SetAllowType](#setallowtype) метод, чтобы указать типы адресов, текущий элемент управления network address может поддерживать. Используйте [CNetAddressCtrl::GetAddress](#getaddress) метод для проверки и проанализировать сетевой адрес, вводимых пользователем. Используйте [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод для отображения сообщения ошибке всплывающую подсказку, если [CNetAddressCtrl::GetAddress](#getaddress) метод завершается неудачно.

Этот метод вызывает [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress) макрос, который описан в пакете Windows SDK. Этот макрос отправляет сообщение NCM_GETADDRESS.

##  <a name="getallowtype"></a>  CNetAddressCtrl::GetAllowType

Получает тип сетевой адрес, который может поддерживать текущий элемент управления network address.

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Побитовое сочетание (OR) флагов, указывающее типы адресов, которые может поддерживать элемент управления сетевым адресом. Дополнительные сведения см. в разделе [NET_STRING](https://msdn.microsoft.com/library/windows/desktop/bb762586).

### <a name="remarks"></a>Примечания

Это сообщение вызывает [NetAddr_GetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getallowtype) макрос, который описан в пакете Windows SDK. Этот макрос отправляет сообщение NCM_GETALLOWTYPE.

##  <a name="setallowtype"></a>  CNetAddressCtrl::SetAllowType

Задает тип сетевой адрес, который может поддерживать текущий элемент управления network address.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*dwAddrMask*|[in] Побитовое сочетание (OR) флагов, указывающее типы адресов, которые может поддерживать элемент управления сетевым адресом. Дополнительные сведения см. в разделе [NET_STRING](https://msdn.microsoft.com/library/windows/desktop/bb762586).|

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если этот метод выполнен успешно; в противном случае — код ошибки COM.

### <a name="remarks"></a>Примечания

Используйте [CNetAddressCtrl::SetAllowType](#setallowtype) метод, чтобы указать типы адресов, которые может поддерживать текущего управления сетевым адресом. Используйте [CNetAddressCtrl::GetAddress](#getaddress) метод для проверки и проанализировать сетевой адрес, вводимых пользователем. Используйте [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) метод для отображения сообщения ошибке всплывающую подсказку, если [CNetAddressCtrl::GetAddress](#getaddress) метод завершается неудачно.

Это сообщение вызывает [NetAddr_SetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_setallowtype) макрос, который описан в пакете Windows SDK. Этот макрос отправляет сообщение NCM_SETALLOWTYPE.

## <a name="see-also"></a>См. также

[Класс CNetAddressCtrl](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CEdit](../../mfc/reference/cedit-class.md)
