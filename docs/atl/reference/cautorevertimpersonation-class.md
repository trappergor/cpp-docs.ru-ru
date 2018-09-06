---
title: Класс CAutoRevertImpersonation | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99f0615dc37070311428ec12894bcaeea8febe8d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760621"
---
# <a name="cautorevertimpersonation-class"></a>Класс CAutoRevertImpersonation

Этот класс возвращает [CAccessToken](../../atl/reference/caccesstoken-class.md) объектов nonimpersonating состояние, когда оно выходит за пределы области.

## <a name="syntax"></a>Синтаксис

```
class CAutoRevertImpersonation
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Создает `CAutoRevertImpersonation` объекта|
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|Уничтожает объект и отменяет олицетворение токена доступа.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAutoRevertImpersonation::Attach](#attach)|Автоматизирует редакция олицетворения маркера доступа.|
|[CAutoRevertImpersonation::Detach](#detach)|Отменяет редакция автоматическое олицетворение.|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Возвращает значение текущего маркера доступа, связанный с данным объектом.|

## <a name="remarks"></a>Примечания

[Маркер доступа](/windows/desktop/SecAuthZ/access-tokens) — это объект, описывающий контекст безопасности процесса или потока и выделяется для каждого вошедшего в систему Windows NT или Windows 2000. Эти маркеры доступа может быть представлено с `CAccessToken` класса.

Иногда бывает необходимо олицетворять маркеры доступа. Этот класс предоставляется для удобства, но он не выполняет олицетворение маркеров доступа; выполняет только автоматическое редакция nonimpersonated состояние. Это обусловлено олицетворение маркер доступа можно выполнить несколькими способами.

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="attach"></a>  CAutoRevertImpersonation::Attach

Автоматизирует редакция олицетворения маркера доступа.

```
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Параметры

*личный маркер доступа*  
Адрес [CAccessToken](../../atl/reference/caccesstoken-class.md) объект автоматически отменены

### <a name="remarks"></a>Примечания

Этот метод следует использовать, только если [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) объект был создан с пустым `CAccessToken` указателем, или если [отсоединения](#detach) был вызван ранее. В простых случаях необязательно для использования этого метода.

##  <a name="cautorevertimpersonation"></a>  CAutoRevertImpersonation::CAutoRevertImpersonation

Создает объект `CAutoRevertImpersonation`.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Параметры

*личный маркер доступа*  
Адрес [CAccessToken](../../atl/reference/caccesstoken-class.md) объект автоматически отменены.

### <a name="remarks"></a>Примечания

Фактический олицетворение маркера доступа должно выполняться отдельно от, а лучше — до создания `CAutoRevertImpersonation` объекта. Олицетворение будут автоматически отменены при `CAutoRevertImpersonation` объект выходит за пределы области.

##  <a name="dtor"></a>  CAutoRevertImpersonation:: ~ CAutoRevertImpersonation

Уничтожает объект и отменяет олицетворение токена доступа.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Примечания

Отменяет любое олицетворение в данный момент, установленный для [CAccessToken](../../atl/reference/caccesstoken-class.md) объект, предоставленный при создании или с помощью [Attach](#attach) метод. Если нет `CAccessToken` имеет связанный, деструктор не оказывает влияния.

##  <a name="detach"></a>  CAutoRevertImpersonation::Detach

Отменяет редакция автоматическое олицетворение.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес ранее назначенного [CAccessToken](../../atl/reference/caccesstoken-class.md), или значение NULL, если ассоциации не существует.

### <a name="remarks"></a>Примечания

Вызов **отсоединения** предотвращает `CAutoRevertImpersonation` объект вернуть олицетворения, в настоящее время действует для [CAccessToken](../../atl/reference/caccesstoken-class.md) объект, связанный с данным объектом. `CAutoRevertImpersonation` Затем можно удалить с помощью не влияет или повторного сопоставления тот же или другой `CAccessToken` с помощью [Attach](#attach).

##  <a name="getaccesstoken"></a>  CAutoRevertImpersonation::GetAccessToken

Возвращает значение текущего маркера доступа, связанный с данным объектом.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес ранее назначенного [CAccessToken](../../atl/reference/caccesstoken-class.md), или значение NULL, если ассоциации не существует.

### <a name="remarks"></a>Примечания

Если этот метод вызывается для целей, которые включают редакция олицетворения из `CAccessToken` объекта, [отсоединения](#detach) следует использовать метод.

## <a name="see-also"></a>См. также

[Пример ATLSecurity](../../visual-cpp-samples.md)   
[Маркеры доступа](/windows/desktop/SecAuthZ/access-tokens)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
