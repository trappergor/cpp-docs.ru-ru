---
title: Класс ICommandTextImpl
ms.date: 11/04/2016
f1_keywords:
- ICommandText
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
- ATL::ICommandTextImpl::m_strCommandText
- ICommandTextImpl<T>::m_strCommandText
- m_strCommandText
- ICommandTextImpl.m_strCommandText
- ICommandTextImpl::m_strCommandText
- ATL::ICommandTextImpl<T>::m_strCommandText
- ATL.ICommandTextImpl.m_strCommandText
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
ms.openlocfilehash: d05af932d5f531a4dab02e7e0ca171f4484891a3
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556326"
---
# <a name="icommandtextimpl-class"></a>Класс ICommandTextImpl

Предоставляет реализацию для [ICommandText](https://docs.microsoft.com/previous-versions/windows/desktop/ms714914(v=vs.85)) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T >
class ATL_NO_VTABLE ICommandTextImpl
   : public ICommandImpl<T, ICommandText>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Команда класс, производный от `ICommandTextImpl`.

## <a name="requirements"></a>Требования

**Заголовок:** altdb.h

## <a name="members"></a>Участники

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[GetCommandText](#getcommandtext)|Возвращает набор при последнем вызове для текста команд [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|
|[SetCommandText](#setcommandtext)|Задает текст команды, заменив существующий текст команды.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_strCommandText](#strcommandtext)|Сохраняет текст команды.|

## <a name="remarks"></a>Примечания

Обязательный интерфейс на команды.

## <a name="getcommandtext"></a> ICommandTextImpl::GetCommandText

Возвращает набор при последнем вызове для текста команд [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetCommandText)(GUID * pguidDialect,
   LPOLESTR * ppwszCommand);
```

#### <a name="parameters"></a>Параметры

См. в разделе [ICommandText::GetCommandText](https://docs.microsoft.com/previous-versions/windows/desktop/ms709825(v=vs.85)) в *справочнике программиста OLE DB*. *PguidDialect* параметр игнорируется методом по умолчанию.

## <a name="setcommandtext"></a> ICommandTextImpl::SetCommandText

Задает текст команды, заменив существующий текст команды.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect,
   LPCOLESTR pwszCommand);
```

#### <a name="parameters"></a>Параметры

См. в разделе [ICommandText::SetCommandText](https://docs.microsoft.com/previous-versions/windows/desktop/ms709757(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="strcommandtext"></a> ICommandTextImpl::m_strCommandText

Хранит строку текста команды.

### <a name="syntax"></a>Синтаксис

```cpp
CComBSTR m_strCommandText;
```

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)