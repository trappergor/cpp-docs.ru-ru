---
title: Класс CPropExchange | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1009daaa378b4630d9fa477488a802a580d769a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390095"
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
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|Меняет местами свойства больших двоичных объектов (BLOB).|
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Меняет местами свойства шрифтов.|
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|Меняет местами свойство между элементом управления и файл.|
|[CPropExchange::ExchangeProp](#exchangeprop)|Меняет местами свойства встроенного типа.|
|[CPropExchange::ExchangeVersion](#exchangeversion)|Меняет местами номер версии элемента управления OLE.|
|[CPropExchange::GetVersion](#getversion)|Возвращает номер версии элемента управления OLE.|
|[CPropExchange::IsAsynchronous](#isasynchronous)|Определяет, если свойство обмена выполнена асинхронно.|
|[CPropExchange::IsLoading](#isloading)|Указывает, выполняется ли свойства загрузки в элемент управления или сохранения из него.|

## <a name="remarks"></a>Примечания

`CPropExchange` не имеет базового класса.

Устанавливает контекст и направление exchange свойство.

Сохраняемости происходит обмен сведения о состоянии элемента управления, как правило, представляется его свойства, от самого элемента управления и более темным.

Платформа создает объект, производный от `CPropExchange` при получит уведомление о том, что свойства элемента управления OLE должны быть загружены из или хранимых для постоянного хранения.

Платформа передает указатель на это `CPropExchange` объект для элемента управления `DoPropExchange` функции. Если вы использовали мастер для создания начальный набор файлов для, элемент управления элемента управления `DoPropExchange` вызовы функций `COleControl::DoPropExchange`. Версии базового класса, меняет местами стандартных свойств элемента управления; можно изменить версию производного класса к свойствам exchange, добавленных в элемент управления.

`CPropExchange` можно использовать для сериализации свойств элемента управления или инициализировать свойства элемента управления после загрузки или создания элементов управления. `ExchangeProp` И `ExchangeFontProp` функции-члены `CPropExchange` могут хранить свойства и загрузить их из разных мультимедиа.

Дополнительные сведения об использовании `CPropExchange`, см. в статье [элементы ActiveX в MFC: страницы свойств](../../mfc/mfc-activex-controls-property-pages.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CPropExchange`

## <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

##  <a name="exchangeblobprop"></a>  CPropExchange::ExchangeBlobProp

Сериализует свойство, которое сохраняет данные больших двоичных объектов (BLOB).

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>Параметры

*pszPropName*<br/>
Имя свойства при обмене.

*phBlob*<br/>
Указатель на переменную, указывающую на котором хранится свойство (переменная обычно является членом класса).

*hBlobDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Считывается значение свойства или записаны, в соответствующих случаях переменная ссылается *phBlob*. Если *hBlobDefault* указан, он будет использоваться как значение свойства по умолчанию. Это значение используется в том случае, если по какой-либо причине происходит сбой сериализации элемента управления.

Функции `CArchivePropExchange::ExchangeBlobProp`, `CResetPropExchange::ExchangeBlobProp`, и `CPropsetPropExchange::ExchangeBlobProp` переопределить этот чистой виртуальной функции.

##  <a name="exchangefontprop"></a>  CPropExchange::ExchangeFontProp

Меняет местами свойства font между среду хранения и управления.

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>Параметры

*pszPropName*<br/>
Имя свойства при обмене.

*шрифт*<br/>
Ссылку на [CFontHolder](../../mfc/reference/cfontholder-class.md) , содержащий свойства шрифта.

*pFontDesc*<br/>
Указатель на [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc) структуру, содержащую значения для инициализации состояния по умолчанию свойства шрифта при *pFontDispAmbient* имеет значение NULL.

*pFontDispAmbient*<br/>
Указатель на `IFontDisp` интерфейс шрифта, используемый для инициализации состояния по умолчанию свойства шрифта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Если свойство font загружается с носителя в элемент управления, характеристики шрифта, извлекаются с носителя и `CFontHolder` объект, упоминаемый в *шрифта* инициализируется с ними. Если свойство font хранится, характеристики в объект font записываются на носитель.

Функции `CArchivePropExchange::ExchangeFontProp`, `CResetPropExchange::ExchangeFontProp`, и `CPropsetPropExchange::ExchangeFontProp` переопределить этот чистой виртуальной функции.

##  <a name="exchangepersistentprop"></a>  CPropExchange::ExchangePersistentProp

Меняет местами свойство между элементом управления и файл.

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>Параметры

*pszPropName*<br/>
Имя свойства при обмене.

*ppUnk*<br/>
Указатель на переменную, содержащую указатель свойства `IUnknown` интерфейса (эта переменная обычно является членом класса).

*IID*<br/>
Идентификатор интерфейса интерфейса в свойство, которое будет использоваться элементом управления.

*pUnkDefault*<br/>
Значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Если свойство загружается из файла в элемент управления, свойство создается и инициализируется из файла. Если это свойство хранится, ее значение записывается в файл.

Функции `CArchivePropExchange::ExchangePersistentProp`, `CResetPropExchange::ExchangePersistentProp`, и `CPropsetPropExchange::ExchangePersistentProp` переопределить этот чистой виртуальной функции.

##  <a name="exchangeprop"></a>  CPropExchange::ExchangeProp

Меняет местами свойство между среду хранения и управления.

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>Параметры

*pszPropName*<br/>
Имя свойства при обмене.

*vtProp*<br/>
Символ, указывающий тип свойства, которые при обмене. Доступны следующие значения:

|Символ|Тип свойства|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_BOOL|**BOOL**|
|VT_BSTR|`CString`|
|VT_CY|**CY**|
|VT_R4|**float**|
|VT_R8|**double**|

*pvProp*<br/>
Указатель на значение свойства.

*pvDefault*<br/>
Указатель на значение по умолчанию для свойства.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если exchange завершилась успешно; 0, если операция завершилась неудачей.

### <a name="remarks"></a>Примечания

Если свойство загружается с носителя в элемент управления, значение свойства извлекается с носителя и хранится в объекте, на которые указывают *pvProp*. Если это свойство хранится на носитель, значение объекта, на которые указывают *pvProp* записывается на носитель.

Функции `CArchivePropExchange::ExchangeProp`, `CResetPropExchange::ExchangeProp`, и `CPropsetPropExchange::ExchangeProp` переопределить этот чистой виртуальной функции.

##  <a name="exchangeversion"></a>  CPropExchange::ExchangeVersion

Вызывается платформой для обработки сохраняемости номера версии.

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>Параметры

*dwVersionLoaded*<br/>
Ссылка на переменную, где будет храниться номер версии постоянные данные, загружаемые.

*dwVersionDefault*<br/>
Текущий номер версии элемента управления.

*bConvert*<br/>
Указывает, следует ли преобразовать постоянных данных в текущей версии или оставить его на той же версии, который был загружен.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае 0.

##  <a name="getversion"></a>  CPropExchange::GetVersion

Вызывайте эту функцию, чтобы получить номер версии элемента управления.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Возвращаемое значение

Номер версии элемента управления.

##  <a name="isasynchronous"></a>  CPropExchange::IsAsynchronous

Определяет, если свойство обмена выполнена асинхронно.

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если свойства обмен которыми осуществляется асинхронно, в противном случае — значение FALSE.

##  <a name="isloading"></a>  CPropExchange::IsLoading

Вызывайте эту функцию, чтобы определить, выполняется ли свойства загрузки в элемент управления или сохранения из него.

```
BOOL IsLoading();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если свойства загружаются; в противном случае 0.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)



