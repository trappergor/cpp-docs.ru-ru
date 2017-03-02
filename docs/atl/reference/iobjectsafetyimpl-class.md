---
title: "Класс IObjectSafetyImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: cff5995555cd069855f9d7becb9eb8367e80c920
ms.lasthandoff: 02/24/2017

---
# <a name="iobjectsafetyimpl-class"></a>Класс IObjectSafetyImpl
Этот класс предоставляет реализацию по умолчанию `IObjectSafety` интерфейс, чтобы клиент мог получить и задать уровни безопасности объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
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
  
- **INTERFACESAFE_FOR_UNTRUSTED_CALLER** интерфейса, определенного [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) параметр `riid` следует создавать безопасные для использования.  
  
- **INTERFACESAFE_FOR_UNTRUSTED_DATA** интерфейса, определенного `SetInterfaceSafetyOptions` параметр `riid` следует создавать безопасные непроверенных данных во время инициализации.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Получает параметры безопасности, поддерживаемые объектом, а также параметры безопасности, установленным для объекта.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Объект становится безопасным для инициализации или сценариев.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Сохраняет текущий уровень безопасности объекта.|  
  
## <a name="remarks"></a>Примечания  
 Класс `IObjectSafetyImpl` предоставляет реализацию по умолчанию `IObjectSafety`. `IObjectSafety` Интерфейс позволяет клиенту получить и задать уровни безопасности объекта. Например, можно вызвать метод веб-браузера **IObjectSafety::SetInterfaceSafetyOptions** для создания элемента управления, инициализации или безопасные.  
  
 Обратите внимание, что использование [IMPLEMENTED_CATEGORY](http://msdn.microsoft.com/library/d898ef34-5684-4709-beb9-7114ddd96674) макрос с **CATID_SafeForScripting** и **CATID_SafeForInitializing** категории компонентов предоставляет альтернативный способ указания, что компонент является безопасной.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="a-namegetinterfacesafetyoptionsa--iobjectsafetyimplgetinterfacesafetyoptions"></a><a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions  
 Получает параметры безопасности, поддерживаемые объектом, а также параметры безопасности, установленным для объекта.  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>Примечания  
 Реализация возвращает соответствующие значения для любой интерфейс, поддерживаемый реализацию объекта **IUnknown::QueryInterface**.  
  
> [!IMPORTANT]
>  Любой объект, который поддерживает `IObjectSafety` отвечает за собственную безопасность и для любого объекта, он делегирует. Программист должен учитывать для учетной записи вопросов, связанных с выполнения кода в контексте пользователя, межузловых сценариев и выполняют проверку подходящий зоны.  
  
 В разделе [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemdwcurrentsafetya--iobjectsafetyimplmdwcurrentsafety"></a><a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety  
 Сохраняет текущий уровень безопасности объекта.  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="a-namesetinterfacesafetyoptionsa--iobjectsafetyimplsetinterfacesafetyoptions"></a><a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterfaceSafetyOptions  
 Объект становится безопасным для инициализации или скриптов, задав [m_dwCurrentSafety](#m_dwcurrentsafety) член соответствующее значение.  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>Примечания  
 Реализация возвращает **E_NOINTERFACE** для любого интерфейса не поддерживается реализацией объекта **IUnknown::QueryInterface**.  
  
> [!IMPORTANT]
>  Любой объект, который поддерживает `IObjectSafety` отвечает за собственную безопасность и для любого объекта, он делегирует. Программист должен учитывать для учетной записи вопросов, связанных с выполнения кода в контексте пользователя, межузловых сценариев и выполняют проверку подходящий зоны.  
  
 В разделе [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IObjectSafety](https://msdn.microsoft.com/library/aa768224.aspx)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

