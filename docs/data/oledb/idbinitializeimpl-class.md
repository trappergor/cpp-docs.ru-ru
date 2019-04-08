---
title: Класс IDBInitializeImpl
ms.date: 11/04/2016
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
- IDBInitializeImpl.IDBInitializeImpl
- IDBInitializeImpl
- IDBInitializeImpl::IDBInitializeImpl
- Initialize
- IDBInitializeImpl::Initialize
- IDBInitializeImpl.Initialize
- IDBInitializeImpl.Uninitialize
- Uninitialize
- IDBInitializeImpl::Uninitialize
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
- ATL::IDBInitializeImpl<T>::m_pCUtlPropInfo
- m_pCUtlPropInfo
- IDBInitializeImpl::m_pCUtlPropInfo
- ATL.IDBInitializeImpl.m_pCUtlPropInfo
- IDBInitializeImpl<T>::m_pCUtlPropInfo
- IDBInitializeImpl.m_pCUtlPropInfo
- ATL::IDBInitializeImpl::m_pCUtlPropInfo
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
ms.openlocfilehash: 3418ce11e1a607d66fee593b32fd3a4b7d197407
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033986"
---
# <a name="idbinitializeimpl-class"></a>Класс IDBInitializeImpl

Предоставляет реализацию для [IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85)) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize
```

### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IDBInitializeImpl`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[IDBInitializeImpl](#idbinitializeimpl)|Конструктор.|

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[Initialize](#initialize)|Запускает службу.|
|[Отменить инициализацию](#uninitialize)|Останавливает службу.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_dwStatus](#dwstatus)|Флаги источника данных.|
|[m_pCUtlPropInfo](#pcutlpropinfo)|Указатель на реализацию свойства DB сведения.|

## <a name="remarks"></a>Примечания

Обязательный интерфейс на объекты источника данных и дополнительный интерфейс для перечислителей.

## <a name="idbinitializeimpl"></a> IDBInitializeImpl::IDBInitializeImpl

Конструктор.

### <a name="syntax"></a>Синтаксис

```cpp
IDBInitializeImpl();
```

### <a name="remarks"></a>Примечания

Инициализирует все члены данных.

## <a name="initialize"></a> IDBInitializeImpl::Initialize

Инициализирует объект источника данных, Подготовка поддержка его свойств.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(Initialize)(void);
```

### <a name="remarks"></a>Примечания

См. в разделе [IDBInitialize::Initialize](/previous-versions/windows/desktop/ms718026(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="uninitialize"></a> IDBInitializeImpl::Uninitialize

Объект, в неинициализированном состоянии источника местах данные путем освобождения внутренних ресурсов, таких как поддержка свойств.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(Uninitialize)(void);
```

### <a name="remarks"></a>Примечания

См. в разделе [IDBInitialize::Uninitialize](/previous-versions/windows/desktop/ms719648(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="dwstatus"></a> IDBInitializeImpl::m_dwStatus

Флаги источника данных.

### <a name="syntax"></a>Синтаксис

```cpp
DWORD m_dwStatus;
```

### <a name="remarks"></a>Примечания

Эти флаги задать или указать состояние различных атрибутов для объекта источника данных. Содержит один или несколько из следующих **перечисления** значения:

```cpp
enum DATASOURCE_FLAGS {
    DSF_MASK_INIT     = 0xFFFFF00F,
    DSF_PERSIST_DIRTY = 0x00000001,
    DSF_INITIALIZED   = 0x00000010,
};
```

|||
|-|-|
|`DSF_MASK_INIT`|Маска, чтобы включить восстановление неинициализированном состоянии.|
|`DSF_PERSIST_DIRTY`|Набор, если объект источника данных требует постоянного хранения (то есть, если будут внесены изменения).|
|`DSF_INITIALIZED`|Набор, если источник данных был инициализирован.|

## <a name="pcutlpropinfo"></a> IDBInitializeImpl::m_pCUtlPropInfo

Указатель на объект реализации свойства DB сведения.

### <a name="syntax"></a>Синтаксис

```cpp
CUtlPropInfo< T >* m_pCUtlPropInfo;
```

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)