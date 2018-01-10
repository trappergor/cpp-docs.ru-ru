---
title: "Класс CAutoRevertImpersonation | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
dev_langs: C++
helpviewer_keywords: CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b1982fc3c8b0d46dfd636cab63be82509fa07f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cautorevertimpersonation-class"></a>Класс CAutoRevertImpersonation
Этот класс возвращает [CAccessToken](../../atl/reference/caccesstoken-class.md) объектов nonimpersonating состояние, когда он покидает область действия.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAutoRevertImpersonation
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Создает `CAutoRevertImpersonation` объекта|  
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|Удаляет объект и возвращается олицетворения маркера доступа.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](#attach)|Автоматизирует возврате олицетворение маркера доступа.|  
|[CAutoRevertImpersonation::Detach](#detach)|Отменяет изменения автоматического олицетворения.|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Извлекает текущий маркера доступа, связанный с данным объектом.|  
  
## <a name="remarks"></a>Примечания  
 [Маркер доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909) — это объект, который описывает контекст безопасности процесса или потока и выделяется для каждого пользователя, зарегистрированного в системе Windows NT или Windows 2000. Эти токены доступа может быть представлено с `CAccessToken` класса.  
  
 Иногда бывает необходимо олицетворение маркера доступа. Этот класс предоставляется для удобства, но он не выполняет олицетворение маркера доступа; выполняет только автоматического изменения версии nonimpersonated состояние. Это происходит потому олицетворение маркер доступа можно выполнить несколькими способами.  
  
 Введение модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="attach"></a>CAutoRevertImpersonation::Attach  
 Автоматизирует возврате олицетворение маркера доступа.  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pAT`  
 Адрес [CAccessToken](../../atl/reference/caccesstoken-class.md) объект автоматически отменена  
  
### <a name="remarks"></a>Примечания  
 Этот метод следует использовать, только если [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) объект был создан со значением NULL `CAccessToken` указателя, или если [отсоединения](#detach) был вызван ранее. В простых случаях не требуется для использования этого метода.  
  
##  <a name="cautorevertimpersonation"></a>CAutoRevertImpersonation::CAutoRevertImpersonation  
 Создает объект `CAutoRevertImpersonation`.  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pAT`  
 Адрес [CAccessToken](../../atl/reference/caccesstoken-class.md) объект автоматически отменена.  
  
### <a name="remarks"></a>Примечания  
 Фактический олицетворение маркера доступа следует выполнять отдельно от и лучше всего до создания `CAutoRevertImpersonation` объекта. Олицетворение будут отменены автоматически при `CAutoRevertImpersonation` объект выходит за пределы области.  
  
##  <a name="dtor"></a>CAutoRevertImpersonation:: ~ CAutoRevertImpersonation  
 Удаляет объект и возвращается олицетворения маркера доступа.  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращается в настоящее время действует для олицетворения [CAccessToken](../../atl/reference/caccesstoken-class.md) объект, предоставленный при создании или посредством [присоединение](#attach) метод. Если не `CAccessToken` имеет связанный, деструктор не оказывает влияния.  
  
##  <a name="detach"></a>CAutoRevertImpersonation::Detach  
 Отменяет изменения автоматического олицетворения.  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес ранее связанного [CAccessToken](../../atl/reference/caccesstoken-class.md), или значение NULL, если совпадения нет.  
  
### <a name="remarks"></a>Примечания  
 Вызов **отсоединения** предотвращает `CAutoRevertImpersonation` объекта вернуть олицетворения, в настоящее время действует для [CAccessToken](../../atl/reference/caccesstoken-class.md) объекта, связанного с данным объектом. `CAutoRevertImpersonation`Затем можно удалить с помощью не влияет или повторно связывать на том же или другом `CAccessToken` с помощью [присоединение](#attach).  
  
##  <a name="getaccesstoken"></a>CAutoRevertImpersonation::GetAccessToken  
 Извлекает текущий маркера доступа, связанный с данным объектом.  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Адрес ранее связанного [CAccessToken](../../atl/reference/caccesstoken-class.md), или значение NULL, если совпадения нет.  
  
### <a name="remarks"></a>Примечания  
 Если этот метод вызывается для целей, включающие изменения версии олицетворения из `CAccessToken` объекта, [отсоединения](#detach) следует использовать метод.  
  
## <a name="see-also"></a>См. также  
 [Пример ATLSecurity](../../visual-cpp-samples.md)   
 [Маркеры доступа](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
