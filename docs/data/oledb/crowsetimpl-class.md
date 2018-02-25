---
title: "Класс CRowsetImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- CRowsetImpl class
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0d97eefdc1885c532df9c9be913e3f1beea2ff09
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimpl-class"></a>Класс CRowsetImpl
Предоставляет стандартную реализацию набора строк OLE DB без необходимости множественное наследование многие реализации интерфейсов.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <  
   class T,  
   class Storage,  
   class CreatorClass,  
   class ArrayType = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class RowsetInterface = IRowsetImpl <T, IRowset>   
>  
class CRowsetImpl :    
   public CComObjectRootEx<CreatorClass::_ThreadModel>,   
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,   
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс пользователя, который является производным от `CRowsetImpl`.  
  
 `Storage`  
 Класс записей пользователя.  
  
 `CreatorClass`  
 Класс, содержащий свойства для набора строк; Обычно команда.  
  
 `ArrayType`  
 Класс, который будет выступать в качестве хранилища для данных в наборе строк. По умолчанию этот параметр `CAtlArray`, но это может быть любой класс, который поддерживает необходимые функциональные возможности.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[NameFromDBID](../../data/oledb/crowsetimpl-namefromdbid.md)|Извлекает строку из **DBID** и копирует его в `bstr` переданный.|  
|[SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)|Проверяет и сохраняет **DBID**s в двух строк ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).|  
  
### <a name="overridable-methods"></a>Переопределяемые методы  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/crowsetimpl-getcolumninfo.md)|Извлекает сведения о столбце для конкретного клиентского запроса.|  
|[GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)|Проверяет, если оба параметра содержат строковые значения и если да, копирует строковые значения членов данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
|[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md)|Проверяет, см. Если один или оба **DBID**s содержать строковые значения и если да, копирует их членах данных [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)|По умолчанию `CAtlArray` , templatizes от аргумента шаблона записи пользователя для `CRowsetImpl`. Можно использовать другой класс типа массива, изменив `ArrayType` аргумент шаблона для `CRowsetImpl`.|  
|[m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)|Содержит команду начального набора строк.|  
|[m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)|Содержит индекс начального набора строк.|  
  
## <a name="remarks"></a>Примечания  
 `CRowsetImpl` предоставляет переопределений в виде статических требуемому типу. Методы управления способом, в котором определенного набора строк будет проверять текст команды. Можно создать свой собственный `CRowsetImpl`-класс стиля, делая реализация интерфейсов нескольких наследуется. Это единственный метод, для которого необходимо предоставить реализация **Execute**. В зависимости от того, какой тип набора строк создается, создатель методы ожидаемых различные подписи для **Execute**. Например, если вы используете `CRowsetImpl`-производный класс для реализации набора строк схемы **Execute** метод будет иметь следующую сигнатуру:  
  
 `HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`  
  
 Если вы создаете `CRowsetImpl`-производный класс для реализации команды или сеанса набор строк, **Execute** метод будет иметь следующую сигнатуру:  
  
 `HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`  
  
 Для реализации любого из `CRowsetImpl`-производный **Execute** методы, необходимо заполнить буферов внутренние данные ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h