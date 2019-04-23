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
ms.openlocfilehash: de9e930056db7b91968ca1ce471a87809693376a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037108"
---
# <a name="icommandtextimpl-class"></a>Класс ICommandTextImpl

Предоставляет реализацию для [ICommandText](/previous-versions/windows/desktop/ms714914(v=vs.85)) интерфейс.

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

См. в разделе [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) в *справочнике программиста OLE DB*. *PguidDialect* параметр игнорируется методом по умолчанию.

## <a name="setcommandtext"></a> ICommandTextImpl::SetCommandText

Задает текст команды, заменив существующий текст команды.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect,
   LPCOLESTR pwszCommand);
```

#### <a name="parameters"></a>Параметры

См. в разделе [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="strcommandtext"></a> ICommandTextImpl::m_strCommandText

Хранит строку текста команды.

### <a name="syntax"></a>Синтаксис

```cpp
CComBSTR m_strCommandText;
```

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)