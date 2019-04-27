---
title: Класс CUtlProps
ms.date: 11/04/2016
f1_keywords:
- CUtlProps
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
- CUtlProps
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
helpviewer_keywords:
- CUtlProps class
- GetPropValue method
- IsValidValue method
- OnInterfaceRequested method
- OnPropertyChanged method
- SetPropValue method
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
ms.openlocfilehash: 3f1af90bcf454a3651dd8de65bbee7cb6b5960ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62176126"
---
# <a name="cutlprops-class"></a>Класс CUtlProps

Реализует свойства для различных интерфейсов свойство OLE DB (например, `IDBProperties`, `IDBProperties`, и `IRowsetInfo`).

## <a name="syntax"></a>Синтаксис

```cpp
template < class T >
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, содержащий `BEGIN_PROPSET_MAP`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[GetPropValue](#getpropvalue)|Получает свойство из набора свойств.|
|[IsValidValue](#isvalidvalue)|Используется для проверки значения перед заданием свойства.|
|[OnInterfaceRequested](#oninterfacerequested)|Обрабатывает запросы к необязательный интерфейс, когда потребитель вызывает метод для создания объекта интерфейса.|
|[OnPropertyChanged](#onpropertychanged)|Вызывается после задания свойства для обработки связанных свойств.|
|[SetPropValue](#setpropvalue)|Задает свойство в наборе свойств.|

## <a name="remarks"></a>Примечания

Большая часть этого класса является элементом реализации.

`CUtlProps` содержит два члена для задания свойств внутренне. [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) и [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).

Дополнительные сведения о макросы, используемые в сопоставление набора свойств, см. в разделе [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) и [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).

## <a name="getpropvalue"></a> CUtlProps::GetPropValue

Получает свойство из набора свойств.

### <a name="syntax"></a>Синтаксис

```cpp
OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>Параметры

*pguidPropSet*<br/>
[in] Идентификатор GUID для набор свойств.

*dwPropId*<br/>
[in] Индекс свойства.

*pvValue*<br/>
[out] Указатель на значение variant, содержащий новое значение свойства.

### <a name="return-value"></a>Возвращаемое значение

`Failure` Сбой и S_OK в случае успешного выполнения.

## <a name="isvalidvalue"></a> CUtlProps::IsValidValue

Используется для проверки значения перед заданием свойства.

### <a name="syntax"></a>Синтаксис

```cpp
virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>Параметры

*iCurSet*<br/>
Индекс в массиве набора свойств. нуль, если есть только одно свойство набор.

*pDBProp*<br/>
Идентификатор свойства и новое значение в [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) структуры.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT. По умолчанию возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Если у вас есть все процедуры проверки, которые вы хотите запустить на значение, которое вы собираетесь использовать для задания свойства, необходимо переопределить эту функцию. Например можно проверить DBPROP_AUTH_PASSWORD из таблицы пароль, чтобы определить, является допустимым значением.

## <a name="oninterfacerequested"></a> CUtlProps::OnInterfaceRequested

Обрабатывает запросы к необязательный интерфейс, когда потребитель вызывает метод на одном из объекта создания интерфейсов.

### <a name="syntax"></a>Синтаксис

```cpp
virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);
```

#### <a name="parameters"></a>Параметры

*riid*<br/>
[in] Идентификатор IID запрошенного интерфейса. Дополнительные сведения см. в описании *riid* параметр `ICommand::Execute` в *Справочник программиста OLE DB по* (в *MDAC SDK*).

### <a name="remarks"></a>Примечания

`OnInterfaceRequested` обрабатывает запросы потребителей к необязательный интерфейс в том случае, когда потребитель вызывает метод на одном из объекта создания интерфейсов (такие как `IDBCreateSession`, `IDBCreateCommand`, `IOpenRowset`, или `ICommand`). Оно задает соответствующее свойство OLE DB для запрошенного интерфейса. Например, если потребитель запрашивает `IID_IRowsetLocate`, `OnInterfaceRequested` задает `DBPROP_IRowsetLocate` интерфейс. Это обеспечивает правильные данные о состоянии во время создания набора строк.

Этот метод вызывается, когда потребитель вызывает метод `IOpenRowset::OpenRowset` или `ICommand::Execute`.

Если объект-получатель открывает объект, а также запрашивает необязательный интерфейс, поставщик следует задать свойство, связанное с этого интерфейса в значение VARIANT_TRUE. Чтобы разрешить обработку свойств `OnInterfaceRequested` вызывается перед поставщика `Execute` вызывается метод. По умолчанию `OnInterfaceRequested` обрабатывает следующие интерфейсы:

- `IRowsetLocate`

- `IRowsetChange`

- `IRowsetUpdate`

- `IConnectionPointContainer`

- `IRowsetScroll`

Если вы хотите обрабатывать другие интерфейсы, переопределите эту функцию в классе источника, сеанс, команду или набор строк данных для функций процесса. Переопределение должны проходить через интерфейсы обычный set или get свойства убедитесь, что установка свойств устанавливает какие-либо связанные свойства (см. в разделе [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).

## <a name="onpropertychanged"></a> CUtlProps::OnPropertyChanged

Вызывается после задания свойства для обработки связанных свойств.

### <a name="syntax"></a>Синтаксис

```cpp
virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>Параметры

*iCurSet*<br/>
Индекс в массиве набора свойств. нуль, если есть только одно свойство набор.

*pDBProp*<br/>
Идентификатор свойства и новое значение в [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) структуры.

### <a name="return-value"></a>Возвращаемое значение

Стандартный HRESULT. По умолчанию возвращает значение S_OK.

### <a name="remarks"></a>Примечания

Если вы хотите обрабатывать связанные свойства, такие как закладки и обновления, значения которых зависят от значения другого свойства, необходимо переопределить эту функцию.

### <a name="example"></a>Пример

В этой функции пользователь получает идентификатор свойства из `DBPROP*` параметра. Теперь можно сравнить идентификатор к свойству в цепочку. Если свойство найдено, `SetProperties` вызывается со свойством, которое теперь устанавливается вместе с другим свойством. В данном случае, если вы получаете `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, или `DBPROP_ORDEREDBOOKMARKS` свойство, можно установить `DBPROP_BOOKMARKS` свойство.

[!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]

## <a name="setpropvalue"></a> CUtlProps::SetPropValue

Задает свойство в наборе свойств.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>Параметры

*pguidPropSet*<br/>
[in] Идентификатор GUID для набор свойств.

*dwPropId*<br/>
[in] Индекс свойства.

*pvValue*<br/>
[in] Указатель на значение variant, содержащий новое значение свойства.

### <a name="return-value"></a>Возвращаемое значение

`Failure` Сбой и S_OK в случае успешного выполнения.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)