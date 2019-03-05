---
title: Класс COleDispatchDriver
ms.date: 11/04/2016
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
helpviewer_keywords:
- COleDispatchDriver [MFC], COleDispatchDriver
- COleDispatchDriver [MFC], AttachDispatch
- COleDispatchDriver [MFC], CreateDispatch
- COleDispatchDriver [MFC], DetachDispatch
- COleDispatchDriver [MFC], GetProperty
- COleDispatchDriver [MFC], InvokeHelper
- COleDispatchDriver [MFC], ReleaseDispatch
- COleDispatchDriver [MFC], SetProperty
- COleDispatchDriver [MFC], m_bAutoRelease
- COleDispatchDriver [MFC], m_lpDispatch
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
ms.openlocfilehash: 22ba71bc0abaefd20cb68d82d4fefe06ab7fa929
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274587"
---
# <a name="coledispatchdriver-class"></a>Класс COleDispatchDriver

Реализует автоматизацию OLE на стороне клиента.

## <a name="syntax"></a>Синтаксис

```
class COleDispatchDriver
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|Создает объект `COleDispatchDriver`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|Присоединяет `IDispatch` соединение `COleDispatchDriver` объекта.|
|[COleDispatchDriver::CreateDispatch](#createdispatch)|Создает `IDispatch` подключения и присоединяет его к `COleDispatchDriver` объекта.|
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|Отсоединяет `IDispatch` подключения, не освобождая его.|
|[COleDispatchDriver::GetProperty](#getproperty)|Получает свойство автоматизации.|
|[COleDispatchDriver::InvokeHelper](#invokehelper)|Вспомогательный метод для вызова методов автоматизации.|
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|Выпуски `IDispatch` подключения.|
|[COleDispatchDriver::SetProperty](#setproperty)|Задает свойство автоматизации.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[COleDispatchDriver::operator =](#operator_eq)|Копирует значение источника в `COleDispatchDriver` объекта.|
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|Получает доступ к базовой `IDispatch` указатель.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|Указывает, следует ли освободить `IDispatch` во время `ReleaseDispatch` или уничтожение объектов.|
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|Указывает указатель на `IDispatch` интерфейс, подключенный к этому `COleDispatchDriver`.|

## <a name="remarks"></a>Примечания

`COleDispatchDriver` не имеет базового класса.

Диспетчерские интерфейсы OLE предоставляют доступ к методам и свойствам объекта. Функции-члены `COleDispatchDriver` подключать, отключать, создания и выпуска диспетчеризации подключение типа `IDispatch`. Другие функции-члены используются переменные списки аргументов для упрощения вызова `IDispatch::Invoke`.

Этот класс можно использовать напрямую, но обычно он используется только классами, созданного с помощью мастера добавления классов. При создании новых классов C++ путем импорта библиотеки типов, новые классы являются производными от `COleDispatchDriver`.

Дополнительные сведения об использовании `COleDispatchDriver`, ознакомьтесь со следующими статьями:

- [Клиенты автоматизации](../../mfc/automation-clients.md)

- [Серверы автоматизации](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`COleDispatchDriver`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="attachdispatch"></a>  COleDispatchDriver::AttachDispatch

Функция-член `AttachDispatch` вызывается для того, чтобы присоединить указатель `IDispatch` к объекту `COleDispatchDriver` . Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

```
void AttachDispatch(
    LPDISPATCH lpDispatch,
    BOOL bAutoRelease = TRUE);
```

### <a name="parameters"></a>Параметры

*lpDispatch*<br/>
Указатель на объект OLE `IDispatch` , который необходимо присоединить к объекту `COleDispatchDriver` .

*bAutoRelease*<br/>
Определяет, следует ли освободить диспетчер, когда этот объект выходит из области действия.

### <a name="remarks"></a>Примечания

Эта функция освобождает все указатели `IDispatch` , которые уже присоединены к объекту `COleDispatchDriver` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

##  <a name="coledispatchdriver"></a>  COleDispatchDriver::COleDispatchDriver

Создает объект `COleDispatchDriver`.

```
COleDispatchDriver();
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);
COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Параметры

*lpDispatch*<br/>
Указатель на объект OLE `IDispatch` , который необходимо присоединить к объекту `COleDispatchDriver` .

*bAutoRelease*<br/>
Определяет, следует ли освободить диспетчер, когда этот объект выходит из области действия.

*dispatchSrc*<br/>
Ссылаться на существующий `COleDispatchDriver` объекта.

### <a name="remarks"></a>Примечания

Формы `COleDispatchDriver`( `LPDISPATCH lpDispatch`, **BOOL**`bAutoRelease` = **TRUE**) подключается [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) интерфейс.

Формы `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) копирует существующий `COleDispatchDriver` объекта и увеличивает счетчик ссылок.

Формы `COleDispatchDriver`() создает `COleDispatchDriver` объекта, но не подключается `IDispatch` интерфейс. Перед использованием `COleDispatchDriver`() без аргументов, необходимо подключить `IDispatch` к нему с помощью [COleDispatchDriver::CreateDispatch](#createdispatch) или [COleDispatchDriver::AttachDispatch](#attachdispatch). Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](#createdispatch).

##  <a name="createdispatch"></a>  COleDispatchDriver::CreateDispatch

Создает объект интерфейса [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) и присоединяет его к объекту `COleDispatchDriver` .

```
BOOL CreateDispatch(
    REFCLSID clsid,
    COleException* pError = NULL);

BOOL CreateDispatch(
    LPCTSTR lpszProgID,
    COleException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*CLSID*<br/>
Идентификатор класса создаваемого объекта подключения `IDispatch` .

*pError*<br/>
Указатель на объект исключения OLE, который будет содержать код состояния, полученный в результате создания.

*lpszProgID*<br/>
Указатель на программный идентификатор, например Excel.Document.5, объекта автоматизации, для которого будет создаваться объект обработки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

##  <a name="detachdispatch"></a>  COleDispatchDriver::DetachDispatch

Отсоединяет текущий `IDispatch` подключения от этого объекта.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на ранее присоединенные OLE `IDispatch` объекта.

### <a name="remarks"></a>Примечания

`IDispatch` Не освобождается.

Дополнительные сведения о типе LPDISPATCH см. в разделе [реализация интерфейса IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

##  <a name="getproperty"></a>  COleDispatchDriver::GetProperty

Получает свойства объекта, указанного параметром *dwDispID*.

```
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Определяет свойство, которое требуется получить.

*vtProp*<br/>
Задает свойство для извлечения. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](#invokehelper).

*pvProp*<br/>
Адрес переменной, которая будет принимать значение свойства. Он должен соответствовать типа, заданного параметром *vtProp*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

##  <a name="invokehelper"></a>  COleDispatchDriver::InvokeHelper

Вызывает метод или свойство, определяемое *dwDispID*, в контексте, определяемом *wFlags*.

```
void AFX_CDECL InvokeHelper(
    DISPID dwDispID,
    WORD wFlags,
    VARTYPE vtRet,
    void* pvRet,
    const BYTE* pbParamInfo, ...);
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Задает вызываемый метод или свойство.

*wFlags*<br/>
Флаги, описывающие контекст вызова `IDispatch::Invoke`. . Список возможных значений см. в разделе *wFlags* параметр в [IDispatch::Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) в пакете Windows SDK.

*vtRet*<br/>
Указывает тип возвращаемого значения. Возможные значения см. в разделе "Примечания".

*pvRet*<br/>
Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типа, заданного параметром *vtRet*.

*pbParamInfo*<br/>
Указатель на заканчивающуюся нулем строку байтов, определяющую типы параметров после *pbParamInfo*.

*...*<br/>
Переменный список параметров, типов, указанных в *pbParamInfo*.

### <a name="remarks"></a>Примечания

*PbParamInfo* параметр указывает типы параметров, передаваемых в метод или свойство. Переменный список аргументов представлен в объявлении синтаксиса как **...** .

Возможные значения для *vtRet* аргумент берутся из перечисления VARENUM. Ниже приведены возможные значения.

|Символ|Возвращаемый тип|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|**CY**|
|VT_DATE|**DATE**|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|**BOOL**|
|VT_VARIANT|**VARIANT**|
|VT_UNKNOWN|LPUNKNOWN|

*PbParamInfo* аргумент является разделенный пробелами список **VTS_** константы. Одно или несколько из этих значений, разделенных пробелами (не запятыми), составляют список параметров функции. Список возможных значений можно получить с помощью макроса [EVENT_CUSTOM](event-maps.md#event_custom) .

Эта функция преобразует параметры в значения VARIANTARG, а затем вызывает [IDispatch::Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) метод. Если вызов `Invoke` завершается сбоем, эта функция создает исключение. Если SCODE (код состояния), возвращаемый `IDispatch::Invoke` является DISP_E_EXCEPTION, эта функция создает [COleException](../../mfc/reference/coleexception-class.md) объект; в противном случае создается исключение [COleDispatchException](../../mfc/reference/coledispatchexception-class.md).

Дополнительные сведения см. в разделе [VARIANTARG](/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [реализация интерфейса IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface), [IDispatch::Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke), и [структуры из кодов ошибок модели COM](/windows/desktop/com/structure-of-com-error-codes) в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](#createdispatch).

##  <a name="m_bautorelease"></a>  COleDispatchDriver::m_bAutoRelease

Значение TRUE, если COM-объекта осуществляется [m_lpDispatch](#m_lpdispatch) автоматически освобождается при [ReleaseDispatch](#releasedispatch) вызывается или если это `COleDispatchDriver` уничтожении объекта.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>Примечания

По умолчанию `m_bAutoRelease` имеет значение TRUE в конструкторе.

Дополнительные сведения о освобождения COM-объектов, см. в разделе [реализации подсчет ссылок](/windows/desktop/com/implementing-reference-counting) и [IUnknown::Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

##  <a name="m_lpdispatch"></a>  COleDispatchDriver::m_lpDispatch

Указатель на `IDispatch` интерфейс, подключенный к этому `COleDispatchDriver`.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>Примечания

`m_lpDispatch` Данные-член — это открытая переменная типа LPDISPATCH.

Дополнительные сведения см. в разделе [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [COleDispatchDriver::AttachDispatch](#attachdispatch).

##  <a name="operator_eq"></a>  COleDispatchDriver::operator =

Копирует значение источника в `COleDispatchDriver` объекта.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Параметры

*dispatchSrc*<br/>
Указатель на существующий `COleDispatchDriver` объекта.

##  <a name="operator_lpdispatch"></a>  COleDispatchDriver::operator LPDISPATCH

Получает доступ к базовой `IDispatch` указатель `COleDispatchDriver` объекта.

```
operator LPDISPATCH();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

##  <a name="releasedispatch"></a>  COleDispatchDriver::ReleaseDispatch

Выпуски `IDispatch` подключения. Дополнительные сведения см. в разделе [реализация интерфейса IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void ReleaseDispatch();
```

### <a name="remarks"></a>Примечания

Если для этого подключения задана автоматического освобождения, эта функция вызывает `IDispatch::Release` перед освобождением интерфейса.

### <a name="example"></a>Пример

  См. в примере [COleDispatchDriver::AttachDispatch](#attachdispatch).

##  <a name="setproperty"></a>  COleDispatchDriver::SetProperty

Задает свойства объекта OLE, определяемое *dwDispID*.

```
void AFX_CDECL SetProperty(
    DISPID dwDispID,
    VARTYPE vtProp, ...);
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Определяет свойство, которое необходимо задать.

*vtProp*<br/>
Определяет тип свойства, которое необходимо задать. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](#invokehelper).

*...*<br/>
Один параметр типа, заданного параметром *vtProp*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC CALCDRIV](../../visual-cpp-samples.md)<br/>
[Пример MFC ACDUAL](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
