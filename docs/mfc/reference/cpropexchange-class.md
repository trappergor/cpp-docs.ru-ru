---
title: Класс CPropExchange
ms.date: 11/04/2016
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
ms.openlocfilehash: 7818b15e502bb32640d6b9dbfe1a6e4927c70650
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363973"
---
# <a name="cpropexchange-class"></a>Класс CPropExchange

Поддерживает реализацию сохранения элементов управления OLE.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPropExchange:ExchangeBlobProp](#exchangeblobprop)|Обменивает свойство двоичного крупного объекта (BLOB).|
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Обменивает свойство шрифта.|
|[CPropExchange:Exchange](#exchangepersistentprop)|Обменивает свойство между элементом управления и файлом.|
|[CPropExchange:ExchangeProp](#exchangeprop)|Обменивает свойства любого встроенного типа.|
|[CPropExchange:Exchange](#exchangeversion)|Обменивает номер версии управления OLE.|
|[CPropExchange:GetVersion](#getversion)|Получает номер версии управления OLE.|
|[CPropExchange::IsAsynchronous](#isasynchronous)|Определяет, осуществляется ли обмен имуществом асинхронно.|
|[CPropExchange::Загрузка](#isloading)|Указывает, загружаются ли свойства в элемент управления или сохраняются из него.|

## <a name="remarks"></a>Remarks

`CPropExchange`не имеет базового класса.

Устанавливает контекст и направление обмена имуществом.

Настойчивость — это обмен информацией о состоянии контроля, обычно представленной его свойствами, между самим элементом управления и средой.

Рамка строит объект, полученный от `CPropExchange` того, когда он уведомляется о том, что свойства управления OLE должны быть загружены из или сохранены в постоянное хранилище.

Фрейм передает указатель `CPropExchange` на этот объект `DoPropExchange` функции элемента управления. Если вы использовали мастера для создания стартовых файлов для `DoPropExchange` управления, функция управления вызывает. `COleControl::DoPropExchange` Версия базового класса обменивается свойствами акций управления; вы изменяете версию вашего производной версии класса для обмена свойствами, которые вы добавили в элемент управления.

`CPropExchange`может использоваться для сериализации свойств элемента управления или инициализации свойств элемента управления при нагрузке или создании элемента управления. `ExchangeProp` Функции `ExchangeFontProp` и `CPropExchange` функции члена могут хранить свойства и загружать их из различных носителей.

Для получения дополнительной `CPropExchange`информации об использовании, см. [MFC ActiveX Controls: Property Pages](../../mfc/mfc-activex-controls-property-pages.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CPropExchange`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="cpropexchangeexchangeblobprop"></a><a name="exchangeblobprop"></a>CPropExchange:ExchangeBlobProp

Сериализирует свойство, в которое хранятся данные бинарных крупных объектов (BLOB).

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>Параметры

*pszPropName*<br/>
Название обмениваемого имущества.

*phBlob*<br/>
Указатель на переменную, указывающую на то, где хранится свойство (переменная обычно является членом вашего класса).

*hBlobDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Значение свойства считывается или записывается, по мере необходимости, переменной, на которую ссылается *phBlob.* Если *hBlobDefault* указан, он будет использоваться в качестве значения по умолчанию. Это значение используется, если по какой-либо причине сериализация элемента управления выходит из строя.

Функции `CArchivePropExchange::ExchangeBlobProp` `CResetPropExchange::ExchangeBlobProp`, `CPropsetPropExchange::ExchangeBlobProp` и переопределить эту чистую виртуальную функцию.

## <a name="cpropexchangeexchangefontprop"></a><a name="exchangefontprop"></a>CPropExchange::ExchangeFontProp

Обменивает свойство шрифта между носителем хранения и элементом управления.

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>Параметры

*pszPropName*<br/>
Название обмениваемого имущества.

*Шрифта*<br/>
Ссылка на объект [CFontHolder,](../../mfc/reference/cfontholder-class.md) содержащий свойство шрифта.

*pFontDesc*<br/>
Указатель на структуру [FONTDESC,](/windows/win32/api/olectl/ns-olectl-fontdesc) содержащую значения для инициализации состояния свойства шрифта по умолчанию, когда *pFontDispAmbient* является NULL.

*pFontDispАмбent*<br/>
Указатель на `IFontDisp` интерфейс шрифта, который будет использоваться для инициализации состояния свойства шрифта по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Если свойство шрифта загружается со среды в элемент управления, характеристики `CFontHolder` шрифта извлекаются из среды, а объект, на который ссылается *шрифт,* инициализируется с ними. При хранении свойства шрифта характеристики объекта шрифта записываются в среду.

Функции `CArchivePropExchange::ExchangeFontProp` `CResetPropExchange::ExchangeFontProp`, `CPropsetPropExchange::ExchangeFontProp` и переопределить эту чистую виртуальную функцию.

## <a name="cpropexchangeexchangepersistentprop"></a><a name="exchangepersistentprop"></a>CPropExchange:Exchange

Обменивает свойство между элементом управления и файлом.

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>Параметры

*pszPropName*<br/>
Название обмениваемого имущества.

*ppUnk*<br/>
Указатель на переменную, содержащую указатель `IUnknown` на интерфейс свойства (эта переменная обычно является членом вашего класса).

*Iid*<br/>
Идентификатор интерфейса на свойстве, которое будет использовать элемент управления.

*pUnkDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Если свойство загружается из файла в управление, свойство создается и инициализируется из файла. При хранении свойства его значение записывается в файл.

Функции `CArchivePropExchange::ExchangePersistentProp` `CResetPropExchange::ExchangePersistentProp`, `CPropsetPropExchange::ExchangePersistentProp` и переопределить эту чистую виртуальную функцию.

## <a name="cpropexchangeexchangeprop"></a><a name="exchangeprop"></a>CPropExchange:ExchangeProp

Обменивает свойство между складским носителем и элементом управления.

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>Параметры

*pszPropName*<br/>
Название обмениваемого имущества.

*vtProp*<br/>
Символ, определяющий тип обмениваемого свойства. Возможны следующие значения:

|Символ|Тип свойства|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**Длинные**|
|VT_BOOL.|**Bool**|
|VT_BSTR|`CString`|
|VT_CY|**CY**|
|VT_R4|**FLOAT**|
|VT_R8|**double**|

*pvProp*<br/>
Указатель на стоимость недвижимости.

*pvDefault*<br/>
Указатель на значение значения по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если обмен был успешным; 0, если не удается.

### <a name="remarks"></a>Remarks

Если свойство загружается из среды в управление, значение свойства извлекается из среды и хранится в объекте, на который указывает *pvProp.* Если свойство хранится в среде, значение объекта, на который указывает *pvProp,* записывается на среду.

Функции `CArchivePropExchange::ExchangeProp` `CResetPropExchange::ExchangeProp`, `CPropsetPropExchange::ExchangeProp` и переопределить эту чистую виртуальную функцию.

## <a name="cpropexchangeexchangeversion"></a><a name="exchangeversion"></a>CPropExchange:Exchange

Вызывается инфраструктурой для обработки сохранения номера версии.

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>Параметры

*dwVersionLoaded*<br/>
Ссылка на переменную, где будет храниться номер версии загруженных постоянных данных.

*dwVersionDefault*<br/>
Текущий номер версии управления.

*bПреобразование*<br/>
Указывает, следует ли преобразовывать постоянные данные в текущую версию или хранить их в той же версии, которая была загружена.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция успешно; 0 в противном случае.

## <a name="cpropexchangegetversion"></a><a name="getversion"></a>CPropExchange:GetVersion

Вызов ими функции для получения номера версии управления.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Возвращаемое значение

Номер версии управления.

## <a name="cpropexchangeisasynchronous"></a><a name="isasynchronous"></a>CPropExchange::IsAsynchronous

Определяет, осуществляется ли обмен имуществом асинхронно.

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если свойства обмениваются асинхронно, в противном случае FALSE.

## <a name="cpropexchangeisloading"></a><a name="isloading"></a>CPropExchange::Загрузка

Вызов исчерпывает эту функцию, чтобы определить, загружаются ли свойства в элемент управления или сохраняются от нее.

```
BOOL IsLoading();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если свойства загружаются; в противном случае 0.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)
