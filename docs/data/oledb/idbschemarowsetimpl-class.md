---
title: Класс IDBSchemaRowsetImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBSchemaRowsetImpl
- CheckRestrictions
- IDBSchemaRowsetImpl::CheckRestrictions
- IDBSchemaRowsetImpl.CheckRestrictions
- IDBSchemaRowsetImpl::CreateSchemaRowset
- ATL::IDBSchemaRowsetImpl::CreateSchemaRowset
- CreateSchemaRowset
- IDBSchemaRowsetImpl.CreateSchemaRowset
- ATL.IDBSchemaRowsetImpl.CreateSchemaRowset
- IDBSchemaRowsetImpl::SetRestrictions
- SetRestrictions
- IDBSchemaRowsetImpl.SetRestrictions
- ATL::IDBSchemaRowsetImpl::GetRowset
- ATL.IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl<SessionClass>::GetRowset
- IDBSchemaRowsetImpl.GetRowset
- IDBSchemaRowsetImpl::GetRowset
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset
- GetRowset
- ATL::IDBSchemaRowsetImpl::GetSchemas
- GetSchemas
- IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- ATL.IDBSchemaRowsetImpl.GetSchemas
- ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas
- IDBSchemaRowsetImpl.GetSchemas
- IDBSchemaRowsetImpl::GetSchemas
dev_langs:
- C++
helpviewer_keywords:
- IDBSchemaRowsetImpl class
- CheckRestrictions method
- CreateSchemaRowset method
- SetRestrictions method
- GetRowset method
- GetSchemas method
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eaea6922f7755295535c0e81d6b9023a10c1317a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339618"
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl - класс
Предоставляет реализацию для наборов строк схемы.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
### <a name="parameters"></a>Параметры  
 *SessionClass*  
 Класс, по которому наследуется `IDBSchemaRowsetImpl` . Как правило, этот класс будет классом сеанса пользователя. 

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CheckRestrictions](#checkrestrictions)|Проверяет допустимость ограничений относительно набора строк схемы.|  
|[CreateSchemaRowset](#createschemarowset)|Реализует функцию создателя COM-объекта для объекта, указанного параметром шаблона.|  
|[SetRestrictions](#setrestrictions)|Указывает, какие ограничения поддерживаются в определенном наборе строк схемы.|  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetRowset](#getrowset)|Возвращает набор строк схемы.|  
|[GetSchemas](#getschemas)|Возвращает список наборов строк схемы, доступных для [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).|  
  
## <a name="remarks"></a>Примечания  
 Этот класс реализует [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) интерфейс и шаблонизируемую функцию создателя [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB использует наборы строк схемы для возврата сведений о данных в поставщике. Такие данные часто называют метаданными. По умолчанию поставщик всегда должен поддерживать `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, и `DBSCHEMA_PROVIDER_TYPES`, как описано в разделе [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) в *Справочник программиста OLE DB по*. Наборы строк схемы назначаются в карте схемы. Сведения о карте записей схемы см. в разделе [SCHEMA_ENTRY](../../data/oledb/schema-entry.md).  
  
 Мастер поставщиков OLE DB в мастере объектов ATL автоматически создает код для наборов строк схемы в проекте. (По умолчанию мастер поддерживает упомянутые выше обязательные наборы строк схемы.) При создании потребителя мастер объектов ATL использует наборы строк схемы для привязки правильных данных к поставщику. Если наборы строк схемы не реализованы для представления правильных метаданных, мастер не выполнит привязку правильных данных.  
  
 Сведения о поддержке наборов строк схемы в поставщике см. в разделе [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md).  
  
 Дополнительные сведения о наборах строк схемы см. в разделе [наборы строк схемы](https://msdn.microsoft.com/library/ms712921.aspx) в *Справочник программиста OLE DB по*.  

## <a name="checkrestrictions"></a> IDBSchemaRowsetImpl::CheckRestrictions
Проверяет допустимость ограничений относительно набора строк схемы.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT CheckRestrictions(REFGUID rguidSchema,  
   ULONG cRestrictions,  const VARIANT rgRestrictions[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 *rguidSchema*  
 [входные данные] Ссылка на запрошенный GUID набора строк схемы (например, `DBSCHEMA_TABLES`).  
  
 *cRestrictions*  
 [входные данные] Число ограничений, переданных потребителем для набора строк схемы.  
  
 *rgRestrictions*  
 [входные данные] Массив длиной *cRestrictions* для задаваемых значений ограничений. Дополнительные сведения см. в описании *rgRestrictions* параметр в [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
### <a name="remarks"></a>Примечания  
 Используйте `CheckRestrictions` для проверки допустимости ограничений для набора строк схемы. Он проверяет ограничения для `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, и `DBSCHEMA_PROVIDER_TYPES` наборы строк схемы. Вызывается для определения, если объект-получатель вызов `IDBSchemaRowset::GetRowset` указано правильно. Если необходима поддержка наборов строк схемы, отличных от перечисленных выше, создайте собственную функцию для выполнения этой задачи.  
  
 `CheckRestrictions` Определяет, если потребитель вызывает [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) с правильным ограничением и правильным типом ограничения (например, VT_BSTR для строки), поддерживаемыми поставщиком. Он также определяет, поддерживается ли правильное количество ограничений. По умолчанию `CheckRestrictions` будет обращаться к поставщику через вызов [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) , ограничения которого он поддерживает в заданном наборе строк. Затем он сравнит ограничения от потребителя с ограничениями, поддерживаемыми поставщиком. Результатом будет успешное или неудачное выполнение.  
  
 Дополнительные сведения о наборах строк схемы см. в разделе [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) в *Справочник программиста OLE DB по* в пакете Windows SDK.  

## <a name="createschemarowset"></a> IDBSchemaRowsetImpl::CreateSchemaRowset
Реализует функцию создателя COM-объекта для объекта, указанного параметром шаблона.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
template template <class SchemaRowsetClass>  
HRESULT CreateSchemaRowset(IUnknown *pUnkOuter,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   SchemaRowsetClass*& pSchemaRowset);  
```  
  
#### <a name="parameters"></a>Параметры  
 *pUnkOuter*  
 [in] Внешний [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) при агрегировании; в противном случае — значение NULL.  
  
 *cRestrictions*  
 [входные данные] Число ограничений, применяемых к набору строк.  
  
 *rgRestrictions*  
 [входные данные] Массив `cRestrictions`**VARIANT**, применяемых к набору строк.  
  
 *riid*  
 [in] Интерфейс [QueryInterface](../../atl/queryinterface.md) для на выходе `IUnknown`.  
  
 *cPropertySets*  
 [входные данные] Число задаваемых наборов свойств.  
  
 *rgPropertySets*  
 [in] Массив [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) структур, определяющих задаваемые свойства.  
  
 *ppRowset*  
 [out] Исходящий `IUnknown` по запросу *riid*. Это `IUnknown` — это интерфейс объекта набора строк схемы.  
  
 *pSchemaRowset*  
 [выходные данные] Указатель на экземпляр класса набора строк схемы. Как правило, этот параметр не используется, но может применяться, если необходимо выполнить дополнительные действия в наборе строк схемы перед передачей его в COM-объект. Время существования *pSchemaRowset* привязана к *ppRowset*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Эта функция реализует универсальный создатель для всех типов наборов строк схемы. Как правило, пользователь не вызывает эту функцию. Ее вызывает реализация карты схемы. 

## <a name="setrestrictions"></a> IDBSchemaRowsetImpl::SetRestrictions
Указывает, какие ограничения поддерживаются в определенном наборе строк схемы.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
void SetRestrictions(ULONG cRestrictions,  
   GUID* /* rguidSchema */,  
   ULONG* rgRestrictions);  
```  
  
#### <a name="parameters"></a>Параметры  
 *cRestrictions*  
 [in] Число ограничений в *rgRestrictions* массива и число GUID в *rguidSchema* массива.  
  
 *rguidSchema*  
 [входные данные] Массив GUID наборов строк схемы, для которого требуется извлечь ограничения. Каждый элемент массива содержит GUID одного набора строк схемы (например, `DBSCHEMA_TABLES`).  
  
 *rgRestrictions*  
 [входные данные] Массив длиной *cRestrictions* для задаваемых значений ограничений. Каждый элемент соответствует ограничениям в наборе строк схемы, определяемом по GUID. Если набор строк схемы не поддерживается поставщиком, элементу присваивается нулевое значение. В противном случае значение **ULONG** значение содержит битовую маску, которая представляет ограничения, поддерживаемые в этом наборе строк схемы. Дополнительные сведения, на котором ограничения соответствуют определенному набору строк схемы, см. в таблице GUID наборов строк схем в [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) в *Справочник программиста OLE DB по* в Windows ПАКЕТ SDK.  
  
### <a name="remarks"></a>Примечания  
 `IDBSchemaRowset` Вызывает `SetRestrictions` для определения ограничений, поддерживаемых в определенном наборе строк схемы (вызывается с помощью [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) через повышенный указатель). Ограничения позволяют выбирать только совпадающие строки (например, поиск всех столбцов в таблице MyTable). Ограничения являются необязательными, и если не поддерживается ни одно ограничение (по умолчанию), всегда возвращаются все данные.  
  
 Реализация по умолчанию этот метод задает *rgRestrictions* массив элементов, равным 0. Чтобы задать ограничения, отличные от используемых по умолчанию, нужно переопределить установку по умолчанию в классе сеанса.  
  
 Сведения о реализации поддержки наборов строк схемы см. в разделе [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md).  
  
 Пример поставщика, поддерживающего наборы строк схемы, см. в примере [UpdatePV](../../visual-cpp-samples.md) .  
  
 Дополнительные сведения о наборах строк схемы см. в разделе [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) в *Справочник программиста OLE DB по* в пакете Windows SDK. 
  
## <a name="getrowset"></a> IDBSchemaRowsetImpl::GetRowset
Возвращает набор строк схемы.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (GetRowset)(IUnknown *pUnkOuter,  
   REFGUID rguidSchema,  
   ULONG cRestrictions,  
   const VARIANT rgRestrictions[],  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown **ppRowset);  
```  
  
#### <a name="parameters"></a>Параметры  
 *pUnkOuter*  
 [in] Внешний `IUnknown` при агрегировании; в противном случае — NULL.  
  
 *rguidSchema*  
 [входные данные] Ссылка на запрошенный GUID набора строк схемы (например, `DBSCHEMA_TABLES`).  
  
 *cRestrictions*  
 [входные данные] Число ограничений, применяемых к набору строк.  
  
 *rgRestrictions*  
 [входные данные] Массив типов `cRestrictions`**VARIANT**, которые представляют ограничения.  
  
 *riid*  
 [входные данные] IID для запроса созданного набора строк схемы.  
  
 *cPropertySets*  
 [входные данные] Число задаваемых наборов свойств.  
  
 *rgPropertySets*  
 [входные/выходные данные] Массив [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) структуры, чтобы установить в созданном наборе строк схемы.  
  
 *ppRowset*  
 [выходные данные] Указатель на запрошенный интерфейс в созданном наборе строк схемы.  
  
### <a name="remarks"></a>Примечания  
 Для реализаций этого метода пользователь должен иметь карту схемы в классе сеанса. С помощью сведений о карте схемы, `GetRowset` создает объект определенного набора строк, если *rguidSchema* параметра равно одному из GUID карты записей. Описание карты записей см. в разделе [SCHEMA_ENTRY](../../data/oledb/schema-entry.md) .  
  
 См. в разделе [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/library/ms722634.aspx) в Windows SDK.  

## <a name="getschemas"></a> IDBSchemaRowsetImpl::GetSchemas
Возвращает список наборов строк схемы, доступных для [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (GetSchema s )(ULONG * pcSchemas,  
   GUID ** prgSchemas,  
   ULONG** prgRest);  
```  
  
#### <a name="parameters"></a>Параметры  
 *pcSchemas*  
 [выходные данные] Указатель на **ULONG** , заполняемый количеством схем.  
  
 *prgSchemas*  
 [выходные данные] Указатель на массив идентификаторов GUID, который заполняется указателем на массив идентификаторов GUID набора строк схемы.  
  
 *prgRest*  
 [выходные данные] Указатель на массив **ULONG**, который должен быть заполнен массивом ограничений.  
  
### <a name="remarks"></a>Примечания  
 Этот метод возвращает массив всех наборов строк схемы, поддерживаемых поставщиком. См. в разделе [IDBSchemaRowset::GetSchemas](https://msdn.microsoft.com/library/ms719605.aspx) в Windows SDK.  
  
 Для реализаций этой функции пользователь должен иметь карту схемы в классе сеанса. Затем с помощью сведений о карте схемы выдается массив идентификаторов GUID для схемы на карте. Он представляет схемы, поддерживаемые поставщиком.  

## <a name="see-also"></a>См. также  
 [Класс IDBSchemaRowsetImpl члены](http://msdn.microsoft.com/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Классы схемы Rowset и Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Поддержка наборов строк схемы](../../data/oledb/supporting-schema-rowsets.md)    
 [SCHEMA_ENTRY](../../data/oledb/schema-entry.md)    
 [UpdatePV](../../visual-cpp-samples.md)