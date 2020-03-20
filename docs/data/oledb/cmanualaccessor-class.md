---
title: Класс CManualAccessor
ms.date: 11/04/2016
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- CManualAccessor.AddBindEntry
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
- ATL::CManualAccessor::CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
- ATL::CManualAccessor::CreateParameterAccessor
- ATL.CManualAccessor.CreateParameterAccessor
- CManualAccessor.CreateParameterAccessor
- CreateParameterAccessor
- CManualAccessor::CreateParameterAccessor
helpviewer_keywords:
- CManualAccessor class
- AddBindEntry method
- AddParameterEntry method
- CreateAccessor method
- CreateParameterAccessor method
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
ms.openlocfilehash: 80c8f94a417c700f86159de53bd53e4011f78d71
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79546071"
---
# <a name="cmanualaccessor-class"></a>Класс CManualAccessor

Представляет тип метода доступа, предназначенный для расширенного использования.

## <a name="syntax"></a>Синтаксис

```cpp
class CManualAccessor : public CAccessorBase
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[AddBindEntry](#addbindentry)|Добавляет запись привязки к выходным столбцам.|
|[аддпараметерентри](#addparameterentry)|Добавляет запись параметра в метод доступа к параметру.|
|[CreateAccessor](#createaccessor)|Выделяет память для структур привязки столбца и инициализирует элементы данных столбца.|
|[креатепараметеракцессор](#createparameteraccessor)|Выделяет память для параметров структуры привязки и инициализирует элементы данных параметров.|

## <a name="remarks"></a>Примечания

С помощью `CManualAccessor`можно указать параметры и привязку выходного столбца с помощью вызовов функций времени выполнения.

## <a name="cmanualaccessoraddbindentry"></a><a name="addbindentry"></a>CManualAccessor:: AddBindEntry

Добавляет запись привязки к выходным столбцам.

### <a name="syntax"></a>Синтаксис

```cpp
void AddBindEntry(DBORDINAL nOrdinal,
   DBTYPE wType,  DBLENGTH nColumnSize,
   void* pData,
   void* pLength = NULL,
   void* pStatus = NULL) throw ();
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер столбца.

*wType*<br/>
окне Тип данных.

*нколумнсизе*<br/>
окне Размер столбца в байтах.

*pData*<br/>
окне Указатель на данные столбца, хранящиеся в буфере.

*пленгс*<br/>
окне Указатель на длину поля, если это необходимо.

*пстатус*<br/>
окне Указатель на переменную, которая должна быть привязана к состоянию столбца, если это необходимо.

### <a name="remarks"></a>Примечания

Чтобы использовать эту функцию, необходимо сначала вызвать [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md). Нельзя добавить больше записей, чем количество столбцов, указанное в `CreateAccessor`.

## <a name="cmanualaccessoraddparameterentry"></a><a name="addparameterentry"></a>CManualAccessor:: Аддпараметерентри

Добавляет запись параметра в структуры записи параметра.

### <a name="syntax"></a>Синтаксис

```cpp
void AddParameterEntry(DBORDINAL nOrdinal,
   DBTYPE wType,  DBLENGTH nColumnSize,
   void* pData,
   void* pLength = NULL,
   void* pStatus = NULL,
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();
```

#### <a name="parameters"></a>Параметры

См. раздел [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) в *справочнике программиста OLE DB*.

*нординал*<br/>
окне Номер параметра.

*wType*<br/>
окне Тип данных.

*нколумнсизе*<br/>
окне Размер столбца в байтах.

*pData*<br/>
окне Указатель на данные столбца, хранящиеся в буфере.

*пленгс*<br/>
окне Указатель на длину поля, если это необходимо.

*пстатус*<br/>
окне Указатель на переменную, которая должна быть привязана к состоянию столбца, если это необходимо.

*епарамио*<br/>
окне Указывает, является ли параметр, с которым связана привязка, входным, входным или выходным параметром.

### <a name="remarks"></a>Примечания

Чтобы использовать эту функцию, необходимо сначала вызвать [креатепараметеракцессор](../../data/oledb/cmanualaccessor-createparameteraccessor.md).

## <a name="cmanualaccessorcreateaccessor"></a><a name="createaccessor"></a>CManualAccessor:: CreateAccessor

Выделяет память для структур привязки столбца и инициализирует элементы данных столбца.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CreateAccessor(int nBindEntries,
  void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>Параметры

*нбиндентриес*<br/>
окне Число столбцов. Это число должно соответствовать числу вызовов функции [CManualAccessor:: AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) .

*pBuffer*<br/>
окне Указатель на буфер, в котором хранятся выходные столбцы.

*нбуфферсизе*<br/>
окне Размер буфера в байтах.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Вызовите эту функцию перед вызовом функции `CManualAccessor::AddBindEntry`.

## <a name="cmanualaccessorcreateparameteraccessor"></a><a name="createparameteraccessor"></a>CManualAccessor:: Креатепараметеракцессор

Выделяет память для параметров структуры привязки и инициализирует элементы данных параметров.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT CreateParameterAccessor(int nBindEntries,
   void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>Параметры

*нбиндентриес*<br/>
окне Число столбцов.

*pBuffer*<br/>
окне Указатель на буфер, в котором хранятся входные столбцы.

*нбуфферсизе*<br/>
окне Размер буфера в байтах.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Эту функцию необходимо вызвать перед вызовом [аддпараметерентри](../../data/oledb/cmanualaccessor-addparameterentry.md).

## <a name="see-also"></a>См. также:

[дбвиевер](../../overview/visual-cpp-samples.md)<br/>
[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс CAccessor](../../data/oledb/caccessor-class.md)<br/>
[Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)