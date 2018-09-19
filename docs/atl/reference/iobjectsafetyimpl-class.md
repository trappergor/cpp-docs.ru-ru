---
title: Класс IObjectSafetyImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e760bab6fb3ad420fc6fe0f5c8a2ea6addc652ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019436"
---
# <a name="iobjectsafetyimpl-class"></a>Класс IObjectSafetyImpl

Этот класс предоставляет реализацию по умолчанию `IObjectSafety` интерфейс, позволяющий клиенту получить и задать уровни безопасности объекта.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IObjectSafetyImpl`.

*dwSupportedSafety*<br/>
Указывает параметры безопасности, поддерживаемых для элемента управления. Может принимать одно из следующих значений:

- Интерфейс, определенный INTERFACESAFE_FOR_UNTRUSTED_CALLER [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) параметр `riid` должно выполняться как безопасные для использования.

- Интерфейс, определенный INTERFACESAFE_FOR_UNTRUSTED_DATA `SetInterfaceSafetyOptions` параметр `riid` следует выполнить безопасный для непроверенных данных во время инициализации.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Получает параметры безопасности, поддерживаемых этим объектом, а также параметры безопасности, заданных в настоящее время для объекта.|
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Объект становится безопасным для инициализации или сценариев.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Сохраняет текущий уровень безопасности объекта.|

## <a name="remarks"></a>Примечания

Класс `IObjectSafetyImpl` предоставляет реализацию по умолчанию `IObjectSafety`. `IObjectSafety` Интерфейс позволяет клиенту получить и задать уровни безопасности объекта. Например, можно вызвать веб-браузер `IObjectSafety::SetInterfaceSafetyOptions` для инициализации или безопасные для использования элемента управления.

Обратите внимание, что использование [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) макрос с помощью категорий компонентов CATID_SafeForScripting и CATID_SafeForInitializing предоставляет альтернативный способ указания, что компонент безопасен.

**Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="getinterfacesafetyoptions"></a>  IObjectSafetyImpl::GetInterfaceSafetyOptions

Получает параметры безопасности, поддерживаемых этим объектом, а также параметры безопасности, заданных в настоящее время для объекта.

```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>Примечания

Реализация возвращает соответствующие значения для любого интерфейса, поддерживаемого реализацией объекта `IUnknown::QueryInterface`.

> [!IMPORTANT]
>  Любой объект, который поддерживает `IObjectSafety` отвечает за собственную безопасность и для любого объекта, он делегирует. Программист должен учитывать учетной записи вопросов, связанных с выполнения кода в контексте пользователя, межузловых сценариев и выполняют проверку подходящий зоны.

См. в разделе [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) в Windows SDK.

##  <a name="m_dwcurrentsafety"></a>  IObjectSafetyImpl::m_dwCurrentSafety

Сохраняет текущий уровень безопасности объекта.

```
DWORD m_dwCurrentSafety;
```

##  <a name="setinterfacesafetyoptions"></a>  IObjectSafetyImpl::SetInterfaceSafetyOptions

Объект становится безопасным для инициализации или скриптов, задав [m_dwCurrentSafety](#m_dwcurrentsafety) элемент с соответствующим значением.

```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>Примечания

Реализация возвращает E_NOINTERFACE для любого интерфейса, не поддерживается реализацией объекта `IUnknown::QueryInterface`.

> [!IMPORTANT]
>  Любой объект, который поддерживает `IObjectSafety` отвечает за собственную безопасность и для любого объекта, он делегирует. Программист должен учитывать учетной записи вопросов, связанных с выполнения кода в контексте пользователя, межузловых сценариев и выполняют проверку подходящий зоны.

См. в разделе [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) в Windows SDK.

## <a name="see-also"></a>См. также

[Интерфейс IObjectSafety](https://msdn.microsoft.com/library/aa768224.aspx)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
