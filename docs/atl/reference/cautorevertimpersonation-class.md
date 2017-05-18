---
title: "Класс CAutoRevertImpersonation | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
dev_langs:
- C++
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: f86f1e5067583b3c4c615c8ca3095e8b67b3fffe
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cautorevertimpersonation-class"></a>Класс CAutoRevertImpersonation
Этот класс возвращает [CAccessToken](../../atl/reference/caccesstoken-class.md) объектов nonimpersonating состоянии, если он выходит за пределы области.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAutoRevertImpersonation
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Создает `CAutoRevertImpersonation` объекта|  
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|Удаляет объект и возвращается олицетворения маркера доступа.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](#attach)|Автоматизирует возврате олицетворения токена доступа.|  
|[CAutoRevertImpersonation::Detach](#detach)|Отменяет изменения автоматического олицетворения.|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Извлекает текущий маркера доступа, связанного с текущим объектом.|  
  
## <a name="remarks"></a>Примечания  
 [Маркер доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909) — это объект, который описывает контекст безопасности процесса или потока и выделяется для каждого пользователя, входившего в системе Windows NT или Windows 2000. Эти маркеры доступа может быть представлено с `CAccessToken` класса.  
  
 Иногда бывает необходимым олицетворение маркера доступа. Этот класс предоставляется для удобства, но он не выполняет олицетворение маркера доступа; выполняет только автоматического восстановления в nonimpersonated состояние. Это вызвано олицетворения маркер доступа можно выполнить несколькими способами.  
  
 Введение в модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="attach"></a>CAutoRevertImpersonation::Attach  
 Автоматизирует возврате олицетворения токена доступа.  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pAT`  
 Адрес [CAccessToken](../../atl/reference/caccesstoken-class.md) , который автоматически отменены  
  
### <a name="remarks"></a>Примечания  
 Этот метод следует использовать, только если [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) объект был создан со значением NULL `CAccessToken` указателя, или если [отсоединения](#detach) был вызван ранее. В простых случаях не требуется для использования этого метода.  
  
##  <a name="cautorevertimpersonation"></a>CAutoRevertImpersonation::CAutoRevertImpersonation  
 Создает объект `CAutoRevertImpersonation`.  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pAT`  
 Адрес [CAccessToken](../../atl/reference/caccesstoken-class.md) , который автоматически отменены.  
  
### <a name="remarks"></a>Примечания  
 Фактический олицетворение маркера доступа следует выполнять отдельно от и предпочтительно до создания `CAutoRevertImpersonation` объекта. Олицетворение будут автоматически отменены при `CAutoRevertImpersonation` объект выходит за пределы области.  
  
##  <a name="dtor"></a>CAutoRevertImpersonation:: ~ CAutoRevertImpersonation  
 Удаляет объект и возвращается олицетворения маркера доступа.  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Восстанавливает олицетворения, в настоящее время действует для [CAccessToken](../../atl/reference/caccesstoken-class.md) объектом, указанным во время создания или через [присоединить](#attach) метод. Если не `CAccessToken` имеет связанный, деструктор не оказывает влияния.  
  
##  <a name="detach"></a>CAutoRevertImpersonation::Detach  
 Отменяет изменения автоматического олицетворения.  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес ранее связанного [CAccessToken](../../atl/reference/caccesstoken-class.md), или значение NULL, если нет никакой связи.  
  
### <a name="remarks"></a>Примечания  
 Вызов **отсоединения** предотвращает `CAutoRevertImpersonation` объекта вернуть любое олицетворение, в настоящее время действует для [CAccessToken](../../atl/reference/caccesstoken-class.md) объект, связанный с данным объектом. `CAutoRevertImpersonation`Затем можно удалить с помощью не влияет или связывания для той же или другой `CAccessToken` с помощью [присоединить](#attach).  
  
##  <a name="getaccesstoken"></a>CAutoRevertImpersonation::GetAccessToken  
 Извлекает текущий маркера доступа, связанного с текущим объектом.  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес ранее связанного [CAccessToken](../../atl/reference/caccesstoken-class.md), или значение NULL, если нет никакой связи.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод вызывается для целей, включающие изменения версии олицетворения из `CAccessToken` объекта, [отсоединения](#detach) следует использовать метод.  
  
## <a name="see-also"></a>См. также  
 [Пример ATLSecurity](../../visual-cpp-samples.md)   
 [Токены доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

