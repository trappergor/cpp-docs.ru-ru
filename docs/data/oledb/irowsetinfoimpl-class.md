---
title: Класс IRowsetInfoImpl
ms.date: 11/04/2016
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
- ATL.IRowsetInfoImpl.GetProperties
- IRowsetInfoImpl.GetProperties
- ATL::IRowsetInfoImpl::GetProperties
- IRowsetInfoImpl::GetProperties
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
helpviewer_keywords:
- IRowsetInfoImpl class
- GetProperties method
- GetReferencedRowset method
- GetSpecification method
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
ms.openlocfilehash: cf72aabce58237f470d536c02727f442404db030
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210448"
---
# <a name="irowsetinfoimpl-class"></a>Класс IRowsetInfoImpl

Предоставляет реализацию для интерфейса [ировсетинфо](/previous-versions/windows/desktop/ms724541(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE IRowsetInfoImpl :
   public IRowsetInfo,
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `IRowsetInfoImpl`.

*пропкласс*<br/>
Определяемый пользователем класс свойств, который по умолчанию имеет значение *T*.

## <a name="requirements"></a>Требования

**Заголовок:** алтдб. h

## <a name="members"></a>Члены

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[GetProperties](#getproperties)|Возвращает текущие значения всех свойств, которые поддерживаются набором строк.|
|[жетреференцедровсет](#getreferencedrowset)|Возвращает указатель интерфейса на набор строк, к которому применяется закладка.|
|[Подробные](#getspecification)|Возвращает указатель интерфейса объекта (команды или сеанса работы), создавшего этот набор строк.|

## <a name="remarks"></a>Remarks

Обязательный интерфейс для наборов строк. Этот класс реализует свойства набора строк с помощью [схемы набора свойств](../../data/oledb/begin-propset-map.md) , определенной в классе команд. Несмотря на то, что класс набора строк использует наборы свойств класса Command, набор строк предоставляется со своей собственной копией свойств времени выполнения, когда он создается объектом команды или сеанса.

## <a name="irowsetinfoimplgetproperties"></a><a name="getproperties"></a>Свойства IRowsetInfoImpl:: Properties

Возвращает текущие параметры для свойств в группе `DBPROPSET_ROWSET`.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetProperties )(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG* pcPropertySets,
   DBPROPSET** prgPropertySets);
```

#### <a name="parameters"></a>Параметры

См. раздел [ировсетинфо:: Properties](/previous-versions/windows/desktop/ms719611(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="irowsetinfoimplgetreferencedrowset"></a><a name="getreferencedrowset"></a>IRowsetInfoImpl:: Жетреференцедровсет

Возвращает указатель интерфейса на набор строк, к которому применяется закладка.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetReferencedRowset )(DBORDINAL iOrdinal,
   REFIID riid,
   IUnknown** ppReferencedRowset);
```

#### <a name="parameters"></a>Параметры

См. раздел [ировсетинфо:: жетреференцедровсет](/previous-versions/windows/desktop/ms721145(v=vs.85)) в *справочнике программиста OLE DB*. Параметр *иординал* должен быть столбцом закладки.

## <a name="irowsetinfoimplgetspecification"></a><a name="getspecification"></a>IRowsetInfoImpl::

Возвращает указатель интерфейса объекта (команды или сеанса работы), создавшего этот набор строк.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetSpecification )(REFIID riid,
   IUnknown** ppSpecification);
```

#### <a name="parameters"></a>Параметры

См. раздел [ировсетинфо::](/previous-versions/windows/desktop/ms716746(v=vs.85)) *IsReference в справочнике программиста OLE DB*.

### <a name="remarks"></a>Remarks

Используйте этот метод совместно с [ижетдатасаурцеимпл](../../data/oledb/igetdatasourceimpl-class.md) для извлечения свойств из объекта источника данных.

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
