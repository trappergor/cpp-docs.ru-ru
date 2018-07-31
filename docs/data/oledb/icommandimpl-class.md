---
title: Класс ICommandImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl
- ICommandImpl::Cancel
- Cancel
- ICommandImpl.Cancel
- ICommandImpl::CancelExecution
- ATL::ICommandImpl::CancelExecution
- ATL.ICommandImpl.CancelExecution
- CancelExecution
- ICommandImpl.CancelExecution
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
- ICommandImpl::Execute
- ICommandImpl.Execute
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
- ATL.ICommandImpl.ICommandImpl
- ATL::ICommandImpl::ICommandImpl
- ICommandImpl
- ICommandImpl::ICommandImpl
- ICommandImpl.ICommandImpl
- ICommandImpl::m_bCancel
- ICommandImpl.m_bCancel
- m_bCancel
- ATL::ICommandImpl::m_bCancel
- ATL.ICommandImpl.m_bCancel
- ICommandImpl::m_bCancelWhenExecuting
- ICommandImpl.m_bCancelWhenExecuting
- ATL::ICommandImpl::m_bCancelWhenExecuting
- m_bCancelWhenExecuting
- ATL.ICommandImpl.m_bCancelWhenExecuting
- ICommandImpl.m_bIsExecuting
- ATL::ICommandImpl::m_bIsExecuting
- m_bIsExecuting
- ATL.ICommandImpl.m_bIsExecuting
- ICommandImpl::m_bIsExecuting
dev_langs:
- C++
helpviewer_keywords:
- ICommandImpl class
- Cancel method
- CancelExecution method
- CreateRowset method
- Execute method
- GetDBSession method
- ICommandImpl constructor
- ICommandImpl class, constructor
- m_bCancel
- m_bCancelWhenExecuting
- m_bIsExecuting
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 07453e3040594332857ba75455b1847a3914fdd2
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337798"
---
# <a name="icommandimpl-class"></a>Класс ICommandImpl
Предоставляет реализацию для [ICommand](https://msdn.microsoft.com/library/ms709737.aspx) интерфейс.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `ICommandImpl`.  
  
 *CommandBase*  
 Интерфейс команды. Значение по умолчанию — `ICommand`.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[Отмена](#cancel)|Отмена выполнения текущей команды.|  
|[CancelExecution](#cancelexecution)|Отмена выполнения текущей команды.|  
|[CreateRowset](#createrowset)|Создает объект набора строк.|  
|[Выполнение](#execute)|Выполняет команду.|  
|[GetDBSession](#getdbsession)|Возвращает указатель интерфейса для сеанса, создавшего команду.|  
|[ICommandImpl](#icommandimpl)|Конструктор.|  
  
### <a name="data-members"></a>Элементы данных  
  
|||  
|-|-|  
|[m_bCancel](#bcancel)|Указывает, является ли команда отменяется.|  
|[m_bCancelWhenExecuting](#bcancelwhenexecuting)|Указывает, является ли команда отменяется при выполнении.|  
|[m_bIsExecuting](#bisexecuting)|Указывает, является ли команда в данный момент.|  
  
## <a name="remarks"></a>Примечания  
 Обязательный интерфейс объекта команды.  
  
## <a name="cancel"></a> ICommandImpl::Cancel
Отмена выполнения текущей команды.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(Cancel)();  
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [ICommand::Cancel](https://msdn.microsoft.com/library/ms714402.aspx) в *справочнике программиста OLE DB*.  

## <a name="cancelexecution"></a> ICommandImpl::CancelExecution
Отмена выполнения текущей команды.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT CancelExecution();  
```  

## <a name="createrowset"></a> ICommandImpl::CreateRowset
Вызывается средой [Execute](../../data/oledb/icommandimpl-execute.md) создать один набор строк.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
template template <class RowsetClass>  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
```  
  
#### <a name="parameters"></a>Параметры  
 *RowsetClass*  
 Член класса шаблона, представляющий пользователя класса набора строк. Как правило, создаются с помощью мастера.  
  
 *pUnkOuter*  
 [in] Указатель на управляющий `IUnknown` интерфейс, если набор строк создается как часть агрегата; в противном случае имеет значение null.  
  
 *riid*  
 [in] Соответствует *riid* в `ICommand::Execute`.  
  
 *pParams*  
 [входные/выходные данные] Соответствует *pParams* в `ICommand::Execute`.  
  
 *pcRowsAffected*  
 Соответствует *pcRowsAffected* в `ICommand::Execute`.  
  
 *ppRowset*  
 [входные/выходные данные] Соответствует *ppRowset* в `ICommand::Execute`.  
  
 *pRowsetObj*  
 [out] Указатель на объект набора строк. Обычно этот параметр не используется, но он может использоваться, если необходимо выполнить дополнительные действия в наборе строк перед его передачей в COM-объект. Время существования *pRowsetObj* привязана к *ppRowset*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT. См. в разделе `ICommand::Execute` список типичных значений.  
  
### <a name="remarks"></a>Примечания  
 Для создания более чем одному набору строк, или оставить свои собственные требования к созданию различных наборов строк, поместите различных вызовов `CreateRowset` изнутри `Execute`.  
  
 См. в разделе [ICommand::Execute](https://msdn.microsoft.com/library/ms718095.aspx) в *справочнике программиста OLE DB.*  

## <a name="execute"></a> ICommandImpl::Execute
Выполняет команду.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Execute(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ICommand::Execute](https://msdn.microsoft.com/library/ms718095.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="remarks"></a>Примечания  
 Исходящий интерфейс, запрошенный будет получен из объекта набора строк, эта функция создает интерфейс.  
  
 `Execute` вызовы [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Переопределите реализацию по умолчанию для создания более одного набора строк или предоставить собственные требования к созданию различных наборов строк.  

## <a name="getdbsession"></a> ICommandImpl::GetDBSession
Возвращает указатель интерфейса для сеанса, создавшего команду.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD (GetDBSession) (REFIID riid,  
   IUnknown** ppSession);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [ICommand::GetDBSession](https://msdn.microsoft.com/library/ms719622.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="remarks"></a>Примечания  
 Удобно использовать для извлечения свойств из сеанса.  

## <a name="icommandimpl"></a> ICommandImpl::ICommandImpl
Конструктор.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
ICommandImpl();  
```  

## <a name="bcancel"></a> ICommandImpl::m_bCancel
Указывает, будет ли отменена команда.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
unsigned m_bCancel:1;  
```  
  
### <a name="remarks"></a>Примечания  
 Вы можете получить эту переменную в `Execute` метод класс команд и "Отмена", соответствующим образом. 

## <a name="bcancelwhenexecuting"></a> ICommandImpl::m_bCancelWhenExecuting
Указывает, можно ли отменить при выполнении команды.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
unsigned m_bCancelWhenExecuting:1;  
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию используется **true** (может быть отменено).  

## <a name="bisexecuting"></a> ICommandImpl::m_bIsExecuting
Указывает, является ли команда в данный момент.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
unsigned m_bIsExecuting:1;  
```  
  
### <a name="remarks"></a>Примечания  
 `Execute` Этой переменной можно задать метод класса команды **true**. 
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)