---
title: Класс CDBPropIDSet | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
- CDBPropIDSet.AddPropertyID
- CDBPropIDSet::AddPropertyID
- AddPropertyID
- ATL.CDBPropIDSet.AddPropertyID
- ATL::CDBPropIDSet::AddPropertyID
- ATL::CDBPropIDSet::CDBPropIDSet
- CDBPropIDSet
- CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet::CDBPropIDSet
- ATL.CDBPropIDSet.CDBPropIDSet
- CDBPropIDSet.operator=
- ATL.CDBPropIDSet.operator=
- ATL::CDBPropIDSet::operator=
- CDBPropIDSet::operator=
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- CDBPropIDSet class
- AddPropertyID method
- CDBPropIDSet class, constructor
- operator =, property sets
- = operator, with OLE DB templates
- operator=, property sets
- SetGUID method
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 111b5ea4f6c25aab2abc4897c9e4bda2a14362a9
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336944"
---
# <a name="cdbpropidset-class"></a>Класс CDBPropIDSet
Наследует от `DBPROPIDSET` структурировать и добавляет конструктор, который инициализирует ключевых полей, а также [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) доступ к методу.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CDBPropIDSet : public tagDBPROPIDSET  
```  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[AddPropertyID](#addpropertyid)|Добавляет свойство в набор свойств идентификатора.|  
|[CDBPropIDSet](#cdbpropidset)|Конструктор.|  
|[SetGUID](#setguid)|Задает идентификатор GUID набора.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#op_equal)|Назначает содержимого идентификатор свойства набора в другой.|  
  
## <a name="remarks"></a>Примечания  
 Использования потребителей OLE DB `DBPROPIDSET` структуры передается массив идентификаторов свойств, для которых необходимо получить сведения о свойстве. Свойств, идентифицированных в одном [DBPROPIDSET](https://msdn.microsoft.com/library/ms717981.aspx) структура принадлежат набору одно свойство.  

## <a name="addpropertyid"></a> CDBPropIDSet::AddPropertyID
Добавляет идентификатор свойства идентификатор набора свойств.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
bool AddPropertyID(DBPROPID propid) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *PropID*  
 [in] Задайте идентификатор свойства, необходимо добавить идентификатор свойства.  

## <a name="cdbpropidset"></a> CDBPropIDSet::CDBPropIDSet
Конструктор. Инициализирует `rgProperties`, `cProperties`и (необязательно) `guidPropertySet` поля [DBPROPIDSET](https://msdn.microsoft.com/library/ms717981.aspx) структуры.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CDBPropIDSet(const GUID& guid);  

CDBPropIDSet(const CDBPropIDSet& propidset);  

CDBPropIDSet();  
```  
  
#### <a name="parameters"></a>Параметры  
 *Идентификатор GUID*  
 [in] Идентификатор GUID, используемый для инициализации `guidPropertySet` поля.  
  
 *propidset*  
 [in] Другой `CDBPropIDSet` объект для копирования.  

## <a name="setguid"></a> CDBPropIDSet::SetGUID
Задает GUID поля в `DBPROPIDSET` структуры.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *Идентификатор GUID*  
 [in] Идентификатор GUID, используемый для задания `guidPropertySet` поле [DBPROPIDSET](https://msdn.microsoft.com/library/ms717981.aspx) структуры.  
  
### <a name="remarks"></a>Примечания  
 Это поле можно задать [конструктор](../../data/oledb/cdbpropidset-cdbpropidset.md) также. Эта функция вызывается в том случае, если вы используете конструктор по умолчанию для этого класса.  

## <a name="op_equal"></a> CDBPropIDSet::operator =
Назначает содержимое задать другой набор свойств ID идентификатор свойства.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
CDBPropIDSet& operator =(CDBPropIDSet& propset) throw();  
```  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)