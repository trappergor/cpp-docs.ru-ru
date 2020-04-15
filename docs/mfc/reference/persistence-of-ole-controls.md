---
title: Сохраняемость элементов управления OLE
ms.date: 11/04/2016
helpviewer_keywords:
- OLE controls [MFC], persistence
- persistence, OLE controls
ms.assetid: 64f8dc80-f110-41af-b3ea-14948f6bfdf7
ms.openlocfilehash: 88707da503b1d1cdc809827dc4d1bac0ccad9b5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373012"
---
# <a name="persistence-of-ole-controls"></a>Сохраняемость элементов управления OLE

Одной из возможностей управления OLE является сохранение свойств (или сериализация), что позволяет управлению OLE читать или записывать значения свойств в файл или поток и из них. Контейнерное приложение может использовать сериализацию для хранения значений свойств элемента управления даже после того, как приложение уничтожило элемент управления. Значения свойств управления OLE могут быть прочитаны из файла или потока, когда новый экземпляр элемента управления создается позднее.

### <a name="persistence-of-ole-controls"></a>Сохраняемость элементов управления OLE

|||
|-|-|
|[PX_Blob](#px_blob)|Обменивается свойством управления, в которое хранятся данные бинарных крупных объектов (BLOB).|
|[PX_Bool](#px_bool)|Обменивает контрольное свойство типа **BOOL.**|
|[PX_Color](#px_color)|Обменивает цветовое свойство элемента управления.|
|[PX_Currency](#px_currency)|Обменивает контрольное свойство типа **CY.**|
|[PX_DataPath](#px_datapath)|Обменивает контрольное свойство типа. `CDataPathProperty`|
|[PX_Double](#px_double)|Обменивает контрольное свойство **типа double.**|
|[PX_Font](#px_font)|Обменивает свойство шрифта элемента управления.|
|[PX_Float](#px_float)|Обменивает элемент управления **поплавком**типа.|
|[PX_IUnknown](#px_iunknown)|Обменивает контрольное свойство неопределенного типа.|
|[PX_Long](#px_long)|Обменивает контрольное свойство типа **длиной.**|
|[PX_Picture](#px_picture)|Обменивает свойство изображения элемента управления.|
|[PX_Short](#px_short)|Обменивает контрольное свойство **краткого**типа.|
|[PX_ULong](#px_ulong)|Обменивает контрольное свойство типа **ULONG.**|
|[PX_UShort](#px_ushort)|Обменивает контрольное свойство типа **USHORT.**|
|[PXstring](#px_string)|Обменивается свойством управления строкой символов.|
|[PX_VBXFontConvert](#px_vbxfontconvert)|Обменивает свойства, связанные с шрифтом управления VBX, на свойство шрифта управления OLE.|

Кроме того, `AfxOleTypeMatchGuid` глобальная функция предоставляется для проверки на соответствие между TYPEDESC и данной GUID.

## <a name="px_blob"></a><a name="px_blob"></a>PX_Blob

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства, которое хранит двоичные данные крупного объекта (BLOB).

```cpp
BOOL PX_Blob(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    HGLOBAL& hBlob,
    HGLOBAL hBlobDefault = NULL);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*hBlob*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*hBlobDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства будет прочитано от или написано к переменной, на которую ссылается *hBlob*, по мере необходимости. Эта переменная должна быть инициализирована до NULL, прежде чем первоначально призвать `PX_Blob` в первый раз (как правило, это может быть сделано в конструкторе элемента управления). Если *hBlobDefault* указан, он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс инициализации или сериализации элемента управления завершается неудачей.

Ручки *hBlob* и *hBlobDefault* относятся к блоку памяти, который содержит следующее:

- DWORD, который содержит длину, в байтах, двоичных данных, которые следуют, а затем сразу же

- Блок памяти, содержащий фактические двоичные данные.

Обратите `PX_Blob` внимание, что при загрузке свойств типа BLOB будет выделять память с помощью API [Windows GlobalAlloc.](/windows/win32/api/winbase/nf-winbase-globalalloc) Вы несете ответственность за освобождение этой памяти. Таким образом, деструктор вашего управления должен вызывать [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) на любых ручках свойств типа BLOB, чтобы освободить любую память, выделенную для вашего управления.

## <a name="px_bool"></a><a name="px_bool"></a>PX_Bool

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства типа BOOL.

```cpp
BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue);

BOOL PX_Bool(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    BOOL& bValue,
    BOOL bDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*bValue*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*bDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства будет считываться или писаться на переменную, на которую ссылается *bValue,* по мере необходимости. Если *bDefault* указан, он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_color"></a><a name="px_color"></a>PX_Color

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства типа OLE_COLOR.

```cpp
BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue);

BOOL PX_Color(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    OLE_COLOR& clrValue,
    OLE_COLOR clrDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*clrValue*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*clrDefault*<br/>
Значение по умолчанию для свойства, определенное разработчиком управления.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства будет считываться или писаться на переменную, на которую ссылается *clrValue,* по мере необходимости. Если *clrDefault* указан, он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_currency"></a><a name="px_currency"></a>PX_Currency

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства **валюты**типа.

```cpp
BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue);

BOOL PX_Currency(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CY& cyValue,
    CY cyDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*cyValue*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*cyDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства будет считываться или писаться на переменную, на которую ссылается *cyValue,* по мере необходимости. Если *cyDefault* указан, он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_datapath"></a><a name="px_datapath"></a>PX_DataPath

Вызов эту функцию в `DoPropExchange` функции элемента элемента управления для сериализации или инициализации свойства пути данных типа [CDataPathProperty.](../../mfc/reference/cdatapathproperty-class.md)

```cpp
BOOL PX_DataPath(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CDataPathProperty& dataPathProperty);

BOOL PX_DataPath(
    CPropExchange* pPX,
    CDataPathProperty& dataPathProperty);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*dataPathProperty*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Свойства пути данных реализуют асинхронные свойства управления. Значение свойства будет считываться или писаться на переменную, на которую ссылается *dataPathProperty,* по мере необходимости.

## <a name="px_double"></a><a name="px_double"></a>PX_Double

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства **двойного**типа.

```cpp
BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue);

BOOL PX_Double(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    double& doubleValue,
    double doubleDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*двойнаястоимость*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*doubleDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или записывается на переменную, на которую ссылается *doubleValue,* по мере необходимости. Если *указано doubleDefault,* он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_font"></a><a name="px_font"></a>PX_Font

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства шрифта типа.

```cpp
BOOL PX_Font(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC FAR* pFontDesc = NULL,
    LPFONTDISP pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*Шрифта*<br/>
Ссылка на `CFontHolder` объект, содержащий свойство шрифта.

*pFontDesc*<br/>
Указатель на `FONTDESC` структуру, содержащую значения для использования в инициализации состояния свойства шрифта по умолчанию, в случае, когда *pFontDispAmbient* является NULL.

*pFontDispАмбent*<br/>
Указатель на `IFontDisp` интерфейс шрифта для использования в инициализации состояния по умолчанию свойства шрифта.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства читается от или `font`написано, ссылка, `CFontHolder` когда это необходимо. Если *pFontDesc* и *pFontDispAmbient* указаны, они используются для инициализации значения по умолчанию, когда это необходимо. Эти значения используются, если по какой-либо причине процесс сериализации элемента управления завершается сбоем. Как правило, вы проходите NULL для *pFontDesc* и окружающего значения, возвращенного `COleControl::AmbientFont` для *pFontDispAmbient.* Обратите внимание, что `COleControl::AmbientFont` объект шрифта, возвращенный, должен быть освобожден вызовом функции `IFontDisp::Release` участника.

## <a name="px_float"></a><a name="px_float"></a>PX_Float

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства **поплавка**типа.

```cpp
BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue);

BOOL PX_Float(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    float& floatValue,
    float floatDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*floatValue*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*floatDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или записывается на переменную, на которую ссылается *floatValue,* по мере необходимости. Если *указано floatDefault,* он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_iunknown"></a><a name="px_iunknown"></a>PX_IUnknown

Вызовите эту функцию `DoPropExchange` в функции элемента элемента управления, чтобы `IUnknown`сериализировать или инициализировать свойство, представленное объектом, имеющим интерфейс, полученный в результате.

```cpp
BOOL PX_IUnknown(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    LPUNKNOWN& pUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault = NULL);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*Панк*<br/>
Ссылка на переменную, содержащую интерфейс объекта, представляющую значение свойства.

*Iid*<br/>
Идентификатор интерфейса с указанием того, какой интерфейс объекта свойства используется элементом управления.

*pUnkDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или записывается на переменную, на которую ссылается *pUnk,* по мере необходимости. Если *pUnkDefault* указан, он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_long"></a><a name="px_long"></a>PX_Long

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства **типа длиной.**

```cpp
BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue);

BOOL PX_Long(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    long& lValue,
    long lDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*Lvalue*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*lDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или записывается на переменную, на которую ссылается *lValue,* по мере необходимости. Если *lDefault* указан, он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_picture"></a><a name="px_picture"></a>PX_Picture

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства изображения вашего элемента управления.

```cpp
BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict);

BOOL PX_Picture(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CPictureHolder& pict,
    CPictureHolder& pictDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*Pict*<br/>
Ссылка на объект [CPictureHolder,](../../mfc/reference/cpictureholder-class.md) где хранится свойство (обычно переменная участника вашего класса).

*pictDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или записывается на переменную, на которую ссылается *pict,* по мере необходимости. Если *указано pictDefault,* он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_short"></a><a name="px_short"></a>PX_Short

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства **краткого**типа.

```cpp
BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue);

BOOL PX_Short(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    short& sValue,
    short sDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*sValue*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*sDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или записывается на переменную, на которую ссылается *sValue,* по мере необходимости. Если *sDefault* указан, он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_ulong"></a><a name="px_ulong"></a>PX_ULong

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства типа **ULONG.**

```cpp
BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue);

BOOL PX_ULong(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    ULONG& ulValue,
    long ulDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*ulValue*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*ulDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или записывается на переменную, на которую ссылается *ulValue,* по мере необходимости. Если *ulDefault* указан, он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_ushort"></a><a name="px_ushort"></a>PX_UShort

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства типа **неподписанных коротких.**

```cpp
BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue);

BOOL PX_UShort(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    USHORT& usValue,
    USHORT usDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*usValue*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*usDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или написано на переменную, на которую ссылается *usValue,* по мере необходимости. Если *указано usDefault,* он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="pxstring"></a><a name="px_string"></a>PXstring

Вызов ими функции `DoPropExchange` в функции элемента элемента управления для сериализации или инициализации свойства строки символов.

```cpp
BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue);

BOOL PXstring(
    CPropExchange* pPX,
    LPCTSTR pszPropName,
    CString& strValue,
    CString strDefault);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*pszPropName*<br/>
Название обмениваемого имущества.

*strValue*<br/>
Ссылка на переменную, в которой хранится свойство (обычно переменная члена вашего класса).

*strDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или записывается на переменную, на которую ссылается *strValue,* по мере необходимости. Если *strDefault* указан, он будет использоваться в качестве значения по умолчанию свойства. Это значение используется, если по какой-либо причине процесс сериализации элемента управления завершается сбоем.

## <a name="px_vbxfontconvert"></a><a name="px_vbxfontconvert"></a>PX_VBXFontConvert

Вызовите эту функцию `DoPropExchange` в функцию элемента управления, чтобы инициализировать свойство шрифта путем преобразования свойств, связанных с шрифтом управления VBX.

```cpp
BOOL PX_VBXFontConvert(
    CPropExchange* pPX,
    CFontHolder& font);
```

### <a name="parameters"></a>Параметры

*Ppx*<br/>
Указатель на объект [CPropExchange](../../mfc/reference/cpropexchange-class.md) (обычно передается `DoPropExchange`в качестве параметра).

*Шрифта*<br/>
Свойство шрифта управления OLE, которое будет содержать переоборудованные свойства, связанные с шрифтом VBX.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Эта функция должна использоваться только элементом управления OLE, который предназначен в качестве прямой замены для управления VBX. Когда среда Visual Basic development преобразует форму, содержащую элемент управления VBX, для использования `IDataObject::SetData` соответствующего элемента управления OL, она вызовет функцию управления, передавая в набор свойств, содержащий данные свойств управления VBX. Эта операция, в свою очередь, `DoPropExchange` приводит к вызову функции управления. `DoPropExchange`может `PX_VBXFontConvert` вызывать для преобразования свойств, связанных с шрифтом управления VBX (например, "FontName", "FontSize" и так далее) в соответствующие компоненты свойства шрифта управления OLE.

`PX_VBXFontConvert`только при преобразовании элемента управления из приложения формы VBX. Пример:

[!code-cpp[NVC_MFCActiveXControl#14](../../mfc/codesnippet/cpp/persistence-of-ole-controls_1.cpp)]
[!code-cpp[NVC_MFCActiveXControl#15](../../mfc/codesnippet/cpp/persistence-of-ole-controls_2.cpp)]

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
