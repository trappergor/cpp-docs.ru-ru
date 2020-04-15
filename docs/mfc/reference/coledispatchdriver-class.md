---
title: Класс ColeDispatchDriver
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
ms.openlocfilehash: c22097c3a686857a6a5698033b7395c5d15f2570
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366081"
---
# <a name="coledispatchdriver-class"></a>Класс ColeDispatchDriver

Реализует автоматизацию OLE на стороне клиента.

## <a name="syntax"></a>Синтаксис

```
class COleDispatchDriver
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeDispatchDriver::COleDispatchDriver](#coledispatchdriver)|Формирует объект `COleDispatchDriver`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeDispatchDriver::AttachDispatch](#attachdispatch)|Прикрепляет `IDispatch` соединение `COleDispatchDriver` к объекту.|
|[ColeDispatchDriver::CreateDispatch](#createdispatch)|Создает `IDispatch` соединение и прикрепляет `COleDispatchDriver` его к объекту.|
|[ColeDispatchDriver::DetachDispatch](#detachdispatch)|Отсоединяет `IDispatch` соединение, не выпуская ее.|
|[ColeDispatchDriver::GetProperty](#getproperty)|Получает свойство автоматизации.|
|[COleDispatchDriver::InvokeHelper](#invokehelper)|Помощник по вызовам методов автоматизации.|
|[ColeDispatchDriver::ReleaseDispatch](#releasedispatch)|Выпускает `IDispatch` соединение.|
|[ColeDispatchDriver::SetProperty](#setproperty)|Устанавливает свойство автоматизации.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[ColeDispatchDriver::оператор](#operator_eq)|Копирует исходное `COleDispatchDriver` значение объекта.|
|[ColeDispatchDriver::оператор LPDISPATCH](#operator_lpdispatch)|Доступ к базовому `IDispatch` указателю.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeDispatchDriver::m_bAutoRelease](#m_bautorelease)|Определяет, следует ли освободить `IDispatch` `ReleaseDispatch` во время или объект уничтожения.|
|[ColeDispatchDriver::m_lpDispatch](#m_lpdispatch)|Указывает указатель на `IDispatch` интерфейс, прикрепленный к этому. `COleDispatchDriver`|

## <a name="remarks"></a>Remarks

`COleDispatchDriver`не имеет базового класса.

Интерфейсы диспетчерской службы OLE обеспечивают доступ к методам и свойствам объекта. Функции `COleDispatchDriver` участника прикрепляют, отсоединяйте, создают `IDispatch`и выпускают диспетчеро-соединение типа. Другие функции участника используют `IDispatch::Invoke`списки переменных аргументов для упрощения вызова.

Этот класс можно использовать напрямую, но обычно используется только классами, созданными мастером Add Class. При создании новых классов СЗ путем импорта библиотеки типов новые классы выводятся из `COleDispatchDriver`.

Для получения дополнительной `COleDispatchDriver`информации об использовании, см.

- [Automation Clients](../../mfc/automation-clients.md)

- [Серверы автоматизации](../../mfc/automation-servers.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`COleDispatchDriver`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="coledispatchdriverattachdispatch"></a><a name="attachdispatch"></a>ColeDispatchDriver::AttachDispatch

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

### <a name="remarks"></a>Remarks

Эта функция освобождает все указатели `IDispatch` , которые уже присоединены к объекту `COleDispatchDriver` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]

## <a name="coledispatchdrivercoledispatchdriver"></a><a name="coledispatchdriver"></a>ColeDispatchDriver::COleDispatchDriver

Формирует объект `COleDispatchDriver`.

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
Ссылка на `COleDispatchDriver` существующий объект.

### <a name="remarks"></a>Remarks

`COleDispatchDriver`Форма `LPDISPATCH lpDispatch`(, **BOOL**`bAutoRelease` = **TRUE**) соединяет интерфейс [IDispatch.](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

Форма `COleDispatchDriver` **(const**`COleDispatchDriver`& `dispatchSrc`) копирует `COleDispatchDriver` существующий объект и приращает значение отсчета ссылок.

Форма `COleDispatchDriver`() создает `COleDispatchDriver` объект, но `IDispatch` не соединяет интерфейс. Перед `COleDispatchDriver`использованием () без аргументов, вы должны `IDispatch` подключиться к нему, используя либо [COleDispatchDriver::CreateDispatch](#createdispatch) или [COleDispatchDriver::AttachDispatch](#attachdispatch). Дополнительные сведения см. в разделе [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](#createdispatch).

## <a name="coledispatchdrivercreatedispatch"></a><a name="createdispatch"></a>ColeDispatchDriver::CreateDispatch

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

*clsid*<br/>
Идентификатор класса создаваемого объекта подключения `IDispatch` .

*pОшибка*<br/>
Указатель на объект исключения OLE, который будет содержать код состояния, полученный в результате создания.

*lpszProgID*<br/>
Указатель на программный идентификатор, например Excel.Document.5, объекта автоматизации, для которого будет создаваться объект обработки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]

## <a name="coledispatchdriverdetachdispatch"></a><a name="detachdispatch"></a>ColeDispatchDriver::DetachDispatch

Отсоединяет текущее `IDispatch` соединение с этим объектом.

```
LPDISPATCH DetachDispatch();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на ранее прилагаемый объект OLE. `IDispatch`

### <a name="remarks"></a>Remarks

Выпущено `IDispatch` не.

Для получения дополнительной информации о [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) типе LPDISPATCH см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]

## <a name="coledispatchdrivergetproperty"></a><a name="getproperty"></a>ColeDispatchDriver::GetProperty

Получает свойство объекта, указанное *dwDispID.*

```
void GetProperty(
    DISPID dwDispID,
    VARTYPE vtProp,
    void* pvProp) const;
```

### <a name="parameters"></a>Параметры

*dwDispID*<br/>
Идентифицирует свойство, подносяе извлечению.

*vtProp*<br/>
Упогоняет свойство, подносиве его. Возможные значения см. в подразделе "Примечания" раздела [COleDispatchDriver::InvokeHelper](#invokehelper).

*pvProp*<br/>
Адрес переменной, которая получит стоимость свойства. Он должен соответствовать типу, указанному *vtProp.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]

## <a name="coledispatchdriverinvokehelper"></a><a name="invokehelper"></a>ColeDispatchDriver:InvokeHelper

Вызывает метод объекта или свойство, указанное *dwDispID,* в контексте, указанном *wFlags*.

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
Флаги, описывающие контекст `IDispatch::Invoke`вызова. . Список возможных значений можно *wFlags* узнать в [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) в SDK Windows.

*vtRet*<br/>
Указывает тип возвращаемого значения. Возможные значения см. в разделе "Примечания".

*pvRet*<br/>
Адрес переменной, которая будет принимать значение свойства или возвращаемое значение. Он должен соответствовать типу, указанному *vtRet.*

*pbParamInfo*<br/>
Указатель на нулевую строку байтов с указанием типов параметров, следующих *pbParamInfo.*

*...*<br/>
Переменный список параметров, типов, указанных в *pbParamInfo*.

### <a name="remarks"></a>Remarks

Параметр *pbParamInfo* определяет типы параметров, передаваемых методу или свойству. Переменный список аргументов представлен в объявлении синтаксиса как **...** .

Возможные значения для аргумента *vtRet* взяты из перечисления VARENUM. Возможны следующие значения:

|Символ|Тип возвращаемых данных|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**Длинные**|
|VT_R4|**FLOAT**|
|VT_R8|**double**|
|VT_CY|**CY**|
|VT_DATE|**Дата**|
|VT_BSTR|BSTR|
|VT_DISPATCH|ЛПЧЛЯп|
|VT_ERROR|SCODE|
|VT_BOOL.|**Bool**|
|VT_VARIANT|**Вариант**|
|VT_UNKNOWN|LPНеизвестный|

Аргумент *pbParamInfo* представляет собой пространственно-разделенный список **VTS_** констант. Одно или несколько из этих значений, разделенных пробелами (не запятыми), составляют список параметров функции. Список возможных значений можно получить с помощью макроса [EVENT_CUSTOM](event-maps.md#event_custom) .

Эта функция преобразует параметры в значения VARIANTARG , а затем вызывает метод [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) . Если вызов `Invoke` завершается сбоем, эта функция создает исключение. Если возвращенный SCODE (код `IDispatch::Invoke` статуса) является DISP_E_EXCEPTION, эта функция бросает объект [COleException;](../../mfc/reference/coleexception-class.md) в противном случае он бросает [COleDispatchException](../../mfc/reference/coledispatchexception-class.md).

Для получения дополнительной информации [см. VARIANTARG](/windows/win32/api/oaidl/ns-oaidl-variant), [Реализация интерфейса IDispatch,](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) [IDispatch::Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke), и [структура кодов ошибки COM](/windows/win32/com/structure-of-com-error-codes) в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [COleDispatchDriver::CreateDispatch](#createdispatch).

## <a name="coledispatchdriverm_bautorelease"></a><a name="m_bautorelease"></a>ColeDispatchDriver::m_bAutoRelease

Если истина, объект COM, доступ к [m_lpDispatch,](#m_lpdispatch) будет автоматически `COleDispatchDriver` выпущен при вызове [ReleaseDispatch](#releasedispatch) или при уничтожении этого объекта.

```
BOOL m_bAutoRelease;
```

### <a name="remarks"></a>Remarks

По умолчанию, `m_bAutoRelease` установлен на TRUE в конструкторе.

Для получения дополнительной информации о выпуске [IUnknown::Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) объектов COM [см.](/windows/win32/com/implementing-reference-counting)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]

## <a name="coledispatchdriverm_lpdispatch"></a><a name="m_lpdispatch"></a>ColeDispatchDriver::m_lpDispatch

Указатель на `IDispatch` интерфейс, прикрепленный `COleDispatchDriver`к этому.

```
LPDISPATCH m_lpDispatch;
```

### <a name="remarks"></a>Remarks

Член `m_lpDispatch` данных является общедоступной переменной типа LPDISPATCH.

Для получения дополнительной [IDispatch](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface) информации см.

### <a name="example"></a>Пример

  Смотрите пример [для COleDispatchDriver::AttachDispatch](#attachdispatch).

## <a name="coledispatchdriveroperator-"></a><a name="operator_eq"></a>ColeDispatchDriver::оператор

Копирует исходное `COleDispatchDriver` значение объекта.

```
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```

### <a name="parameters"></a>Параметры

*dispatchSrc*<br/>
Указатель на существующий `COleDispatchDriver` объект.

## <a name="coledispatchdriveroperator-lpdispatch"></a><a name="operator_lpdispatch"></a>ColeDispatchDriver::оператор LPDISPATCH

Доступ к базовому `IDispatch` указателю `COleDispatchDriver` объекта.

```
operator LPDISPATCH();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]

## <a name="coledispatchdriverreleasedispatch"></a><a name="releasedispatch"></a>ColeDispatchDriver::ReleaseDispatch

Выпускает `IDispatch` соединение. Для получения дополнительной [информации см.](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

```
void ReleaseDispatch();
```

### <a name="remarks"></a>Remarks

Если для этого соединения установлен автоматический `IDispatch::Release` релиз, эта функция вызывает вызов перед выпуском интерфейса.

### <a name="example"></a>Пример

  Смотрите пример [для COleDispatchDriver::AttachDispatch](#attachdispatch).

## <a name="coledispatchdriversetproperty"></a><a name="setproperty"></a>ColeDispatchDriver::SetProperty

Устанавливает свойство объекта OLE, указанное *dwDispID.*

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
Единый параметр типа, указанный *vtProp*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Пример CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец ACDUAL](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
