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
ms.openlocfilehash: 91b273e8bfda6c050fa3d9d6db7aafffbe03d684
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077625"
---
# <a name="icommandimpl-class"></a>Класс ICommandImpl

Предоставляет реализацию для [ICommand](/previous-versions/windows/desktop/ms709737) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class CommandBase = ICommand>
class ATL_NO_VTABLE ICommandImpl : public CommandBase
```

### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `ICommandImpl`.

*CommandBase*<br/>
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
|[Execute](#execute)|Выполняет команду.|
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

См. в разделе [ICommand::Cancel](/previous-versions/windows/desktop/ms714402) в *справочнике программиста OLE DB*.

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

*RowsetClass*<br/>
Член класса шаблона, представляющий пользователя класса набора строк. Как правило, создаются с помощью мастера.

*pUnkOuter*<br/>
[in] Указатель на управляющий `IUnknown` интерфейс, если набор строк создается как часть агрегата; в противном случае имеет значение null.

*riid*<br/>
[in] Соответствует *riid* в `ICommand::Execute`.

*pParams*<br/>
[входные/выходные данные] Соответствует *pParams* в `ICommand::Execute`.

*pcRowsAffected*<br/>
Соответствует *pcRowsAffected* в `ICommand::Execute`.

*ppRowset*<br/>
[входные/выходные данные] Соответствует *ppRowset* в `ICommand::Execute`.

*pRowsetObj*<br/>
[out] Указатель на объект набора строк. Обычно этот параметр не используется, но он может использоваться, если необходимо выполнить дополнительные действия в наборе строк перед его передачей в COM-объект. Время существования *pRowsetObj* привязана к *ppRowset*.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT. См. в разделе `ICommand::Execute` список типичных значений.

### <a name="remarks"></a>Примечания

Для создания более чем одному набору строк, или оставить свои собственные требования к созданию различных наборов строк, поместите различных вызовов `CreateRowset` изнутри `Execute`.

См. в разделе [ICommand::Execute](/previous-versions/windows/desktop/ms718095) в *справочнике программиста OLE DB.*

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

См. в разделе [ICommand::Execute](/previous-versions/windows/desktop/ms718095) в *справочнике программиста OLE DB*.

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

См. в разделе [ICommand::GetDBSession](/previous-versions/windows/desktop/ms719622) в *справочнике программиста OLE DB*.

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

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)