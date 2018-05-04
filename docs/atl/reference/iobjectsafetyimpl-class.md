---
title: Класс IObjectSafetyImpl | Документы Microsoft
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
ms.openlocfilehash: 592a23286ad6592bc0ce6faab999cb362aac42f1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
 `T`  
 Класс, производный от `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Задает параметры безопасности, поддерживаемые для элемента управления. Может принимать одно из следующих значений:  
  
- **INTERFACESAFE_FOR_UNTRUSTED_CALLER** интерфейс, определенный [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) параметр `riid` должны вноситься безопасные для использования.  
  
- **INTERFACESAFE_FOR_UNTRUSTED_DATA** интерфейс, определенный `SetInterfaceSafetyOptions` параметр `riid` должен выполняться безопасным для ненадежных данных во время инициализации.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Возвращает параметры безопасности, поддерживаемые объектом, а также параметры безопасности, установленным для объекта.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|При этом объект становится безопасным для инициализации или сценариев.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Сохраняет текущий уровень безопасности объекта.|  
  
## <a name="remarks"></a>Примечания  
 Класс `IObjectSafetyImpl` предоставляет реализацию по умолчанию `IObjectSafety`. `IObjectSafety` Интерфейс позволяет клиенту получить и задать уровни безопасности объекта. Например, можно вызвать веб-браузер **IObjectSafety::SetInterfaceSafetyOptions** для создания элемента управления, инициализации или безопасные для использования.  
  
 Обратите внимание, что использование [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) макрос с **CATID_SafeForScripting** и **CATID_SafeForInitializing** является альтернативой категорий компонентов способ указания, что компонент безопасна.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>  IObjectSafetyImpl::GetInterfaceSafetyOptions  
 Возвращает параметры безопасности, поддерживаемые объектом, а также параметры безопасности, установленным для объекта.  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>Примечания  
 Реализация возвращает соответствующие значения для любой интерфейс, поддерживаемый реализацию объекта **IUnknown::QueryInterface**.  
  
> [!IMPORTANT]
>  Любой объект, который поддерживает `IObjectSafety` отвечает за собственный уровень безопасности и что любого объекта, он делегирует. Программист должен учитывать для учетной записи вопросов, связанных с выполнением кода в контексте пользователя, межсайтовых сценариев и выполняют проверку подходящий зоны.  
  
 В разделе [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) в Windows SDK.  
  
##  <a name="m_dwcurrentsafety"></a>  IObjectSafetyImpl::m_dwCurrentSafety  
 Сохраняет текущий уровень безопасности объекта.  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>  IObjectSafetyImpl::SetInterfaceSafetyOptions  
 При этом объект становится безопасным для инициализации или скриптов, задав [m_dwCurrentSafety](#m_dwcurrentsafety) член соответствующее значение.  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>Примечания  
 Реализация возвращает **E_NOINTERFACE** для любого интерфейса не поддерживает реализацию объекта **IUnknown::QueryInterface**.  
  
> [!IMPORTANT]
>  Любой объект, который поддерживает `IObjectSafety` отвечает за собственный уровень безопасности и что любого объекта, он делегирует. Программист должен учитывать для учетной записи вопросов, связанных с выполнением кода в контексте пользователя, межсайтовых сценариев и выполняют проверку подходящий зоны.  
  
 В разделе [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IObjectSafety](https://msdn.microsoft.com/library/aa768224.aspx)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
