---
title: Класс Ципаддрессктрл
ms.date: 11/04/2016
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
ms.openlocfilehash: fe8e3109b110c27ab32dc1a4f9a132f1e1c18638
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505814"
---
# <a name="cipaddressctrl-class"></a>Класс Ципаддрессктрл

Предоставляет функциональные возможности стандартного элемента управления "IP-адрес" Windows.

## <a name="syntax"></a>Синтаксис

```
class CIPAddressCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ципаддрессктрл:: Ципаддрессктрл](#cipaddressctrl)|Создает объект `CIPAddressCtrl`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ципаддрессктрл:: Клеараддресс](#clearaddress)|Очищает содержимое элемента управления "IP-адрес".|
|[Ципаддрессктрл:: Create](#create)|Создает элемент управления IP-адреса и прикрепляет его к `CIPAddressCtrl` объекту.|
|[Ципаддрессктрл:: Креатикс](#createex)|Создает элемент управления IP-адреса с указанными расширенными стилями Windows и прикрепляет `CIPAddressCtrl` его к объекту.|
|[Ципаддрессктрл:: наадресовать](#getaddress)|Извлекает значения адреса для всех четырех полей в элементе управления IP-адреса.|
|[Ципаддрессктрл:: Blank](#isblank)|Определяет, являются ли все поля в элементе управления "IP-адрес" пустыми.|
|[Ципаддрессктрл:: Сетаддресс](#setaddress)|Задает значения адреса для всех четырех полей в элементе управления "IP-адрес".|
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Устанавливает фокус клавиатуры на указанное поле в элементе управления IP-адреса.|
|[Ципаддрессктрл:: Сетфиелдранже](#setfieldrange)|Задает диапазон в указанном поле в элементе управления IP-адреса.|

## <a name="remarks"></a>Примечания

Элемент управления IP-адреса, аналогичный элементу управления Edit, позволяет вводить числовой адрес в формате протокола Интернета (IP) и управлять им.

Этот элемент управления (и, `CIPAddressCtrl` следовательно, класс) доступен только для программ, работающих под управлением Microsoft Internet Explorer 4,0 и более поздних версий. Они также будут доступны в будущих версиях Windows и Windows NT.

Дополнительные общие сведения об элементе управления IP-адресом см. в разделе [элементы управления IP-адресами](/windows/win32/Controls/ip-address-controls) в Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

##  <a name="cipaddressctrl"></a>Ципаддрессктрл:: Ципаддрессктрл

Создает объект `CIPAddressCtrl`.

```
CIPAddressCtrl();
```

##  <a name="clearaddress"></a>Ципаддрессктрл:: Клеараддресс

Очищает содержимое элемента управления "IP-адрес".

```
void ClearAddress();
```

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_CLEARADDRESS](/windows/win32/Controls/ipm-clearaddress), как описано в Windows SDK.

##  <a name="create"></a>Ципаддрессктрл:: Create

Создает элемент управления IP-адреса и прикрепляет его к `CIPAddressCtrl` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Стиль элемента управления IP-адресом. Применить сочетание стилей окна. Необходимо включить стиль WS_CHILD, поскольку элемент управления должен быть дочерним окном. Список стилей Windows см. в разделе [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в Windows SDK.

*rect*<br/>
Ссылка на размер и расположение элемента управления IP-адреса. Это может быть либо объект [крект](../../atl-mfc-shared/reference/crect-class.md) , либо структура [Rect](/previous-versions/dd162897\(v=vs.85\)) .

*ппарентвнд*<br/>
Указатель на родительское окно элемента управления IP-адресом. Оно не должно иметь значение NULL.

*nID*<br/>
Идентификатор элемента управления IP-адреса.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

`CIPAddressCtrl` Объект создается в два этапа.

1. Вызовите конструктор, который создает `CIPAddressCtrl` объект.

1. Вызовите метод `Create`, который создает элемент управления IP-адреса.

Если вы хотите использовать расширенные стили Windows с элементом управления, вызовите [креатикс](#createex) вместо `Create`.

##  <a name="createex"></a>Ципаддрессктрл:: Креатикс

Вызовите эту функцию, чтобы создать элемент управления (дочернее окно) и связать `CIPAddressCtrl` его с объектом.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двексстиле*<br/>
Задает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе параметр *двексстиле* для [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в Windows SDK.

*двстиле*<br/>
Стиль элемента управления IP-адресом. Применить сочетание стилей окна. Необходимо включить стиль WS_CHILD, поскольку элемент управления должен быть дочерним окном. Список стилей Windows см. в разделе [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в Windows SDK.

*rect*<br/>
Ссылка на структуру [Rect](/previous-versions/dd162897\(v=vs.85\)) , описывающую размер и расположение создаваемого окна в клиентских координатах *ппарентвнд*.

*ппарентвнд*<br/>
Указатель на окно, которое является родительским элементом управления.

*nID*<br/>
Идентификатор дочернего окна элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [CREATE](#create) , чтобы применить расширенные стили Windows, заданные в расширенном стиле Windows в качестве префикса **WS_EX_** .

##  <a name="getaddress"></a>Ципаддрессктрл:: наадресовать

Извлекает значения адреса для всех четырех полей в элементе управления IP-адреса.

```
int GetAddress(
    BYTE& nField0,
    BYTE& nField1,
    BYTE& nField2,
    BYTE& nField3);

int GetAddress(DWORD& dwAddress);
```

### <a name="parameters"></a>Параметры

*nField0*<br/>
Ссылка на значение поля 0 из упакованного IP-адреса.

*nField1*<br/>
Ссылка на значение поля 1 из упакованного IP-адреса.

*nField2*<br/>
Ссылка на значение поля 2 из упакованного IP-адреса.

*nField3*<br/>
Ссылка на значение поля 3 из упакованного IP-адреса.

*дваддресс*<br/>
Ссылка на адрес значения DWORD, получающего IP-адрес. См. **Примечания** к таблице, в которой показано, как *дваддресс* заполняется.

### <a name="return-value"></a>Возвращаемое значение

Число непустых полей в элементе управления "IP-адрес".

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress), как описано в Windows SDK. В первом приведенном выше прототипе числа в полях от 0 до 3 элемента управления считываются слева направо, заполняют четыре параметра. Во втором приведенном выше прототипе *дваддресс* заполняется следующим образом.

|Поле|Биты, содержащие значение поля|
|-----------|-------------------------------------|
|0|от 24 до 31|
|1|от 16 до 23|
|2|от 8 до 15|
|3|от 0 до 7|

##  <a name="isblank"></a>Ципаддрессктрл:: Blank

Определяет, являются ли все поля в элементе управления "IP-адрес" пустыми.

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если все поля управления IP-адресами пусты; в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_ISBLANK](/windows/win32/Controls/ipm-isblank), как описано в Windows SDK.

##  <a name="setaddress"></a>Ципаддрессктрл:: Сетаддресс

Задает значения адреса для всех четырех полей в элементе управления "IP-адрес".

```
void SetAddress(
    BYTE nField0,
    BYTE nField1,
    BYTE nField2,
    BYTE nField3);

void SetAddress(DWORD dwAddress);
```

### <a name="parameters"></a>Параметры

*nField0*<br/>
Значение поля 0 из упакованного IP-адреса.

*nField1*<br/>
Значение поля 1 из упакованного IP-адреса.

*nField2*<br/>
Значение поля 2 из упакованного IP-адреса.

*nField3*<br/>
Значение поля 3 из упакованного IP-адреса.

*дваддресс*<br/>
Значение типа DWORD, содержащее новый IP-адрес. См. раздел **Примечания** для таблицы, в которой показано, как заполняется значение DWORD.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress), как описано в Windows SDK. В первом приведенном выше прототипе числа в полях от 0 до 3 элемента управления считываются слева направо, заполняют четыре параметра. Во втором приведенном выше прототипе *дваддресс* заполняется следующим образом.

|Поле|Биты, содержащие значение поля|
|-----------|-------------------------------------|
|0|от 24 до 31|
|1|от 16 до 23|
|2|от 8 до 15|
|3|от 0 до 7|

##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus

Устанавливает фокус клавиатуры на указанное поле в элементе управления IP-адреса.

```
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>Параметры

*нфиелд*<br/>
Отсчитываемый от нуля индекс поля, к которому должен быть установлен фокус. Если это значение больше числа полей, фокус устанавливается на первое пустое поле. Если все поля не пусты, фокус устанавливается на первое поле.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_SETFOCUS](/windows/win32/Controls/ipm-setfocus), как описано в Windows SDK.

##  <a name="setfieldrange"></a>Ципаддрессктрл:: Сетфиелдранже

Задает диапазон в указанном поле в элементе управления IP-адреса.

```
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>Параметры

*нфиелд*<br/>
Отсчитываемый от нуля индекс поля, к которому будет применен диапазон.

*нловер*<br/>
Ссылка на целое число, получающее нижнюю границу указанного поля в этом элементе управления IP-адресов.

*нуппер*<br/>
Ссылка на целое число, получающее верхний предел указанного поля в этом элементе управления IP-адресов.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [IPM_SETRANGE](/windows/win32/Controls/ipm-setrange), как описано в Windows SDK. Используйте два параметра, *нловер* и *нуппер*, чтобы указать нижний и верхний пределы поля, а не параметр *вранже* , используемый вместе с сообщением Win32.

## <a name="see-also"></a>См. также

[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
