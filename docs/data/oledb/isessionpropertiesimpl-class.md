---
title: Класс ISessionPropertiesImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- GetProperties
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3759b67ef5d9ee9832649b3b0d516dbfb04440b
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322024"
---
# <a name="isessionpropertiesimpl-class"></a>Класс ISessionPropertiesImpl
Предоставляет реализацию [ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `ISessionPropertiesImpl`.  
  
 *PropClass*  
 Класс определяемые пользователем свойства, который по умолчанию используется *T*.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetProperties](#getproperties)|Возвращает список свойств в группе свойств сеанса, в настоящее время заданы в сеансе.|  
|[SetProperties](#setproperties)|Задает свойства в группе свойств сеанса.|  
  
## <a name="remarks"></a>Примечания  
 Обязательный интерфейс для сеансов. Этот класс реализует свойства сеанса, вызвав статические функции, определенной на [сопоставление набора свойств](../../data/oledb/begin-propset-map.md). Сопоставление набора свойств должен быть указан в классе сеанса.  
  
## <a name="getproperties"></a> ISessionPropertiesImpl::GetProperties
Возвращает список свойств в `DBPROPSET_SESSION` группу свойств, заданных в настоящее время на сеанс.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(GetProperties)(ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ISessionProperties::GetProperties](https://msdn.microsoft.com/library/ms723643.aspx) в *справочнике программиста OLE DB*. 

## <a name="setproperties"></a> ISessionPropertiesImpl::SetProperties
Задает свойства в `DBPROPSET_SESSION` группу свойств.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ISessionProperties::SetProperties](https://msdn.microsoft.com/library/ms714405.aspx) в *справочнике программиста OLE DB*.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
