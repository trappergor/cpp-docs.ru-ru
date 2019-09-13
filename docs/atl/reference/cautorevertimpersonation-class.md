---
title: Класс Кауторевертимперсонатион
ms.date: 11/04/2016
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
ms.openlocfilehash: f1941bfcd7689ab9d22f5094af0eb833a84dab6b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497688"
---
# <a name="cautorevertimpersonation-class"></a>Класс Кауторевертимперсонатион

Этот класс возвращает объекты [CAccessToken](../../atl/reference/caccesstoken-class.md) в неолицетворенное состояние, если оно выходит за пределы области.

## <a name="syntax"></a>Синтаксис

```
class CAutoRevertImpersonation
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Кауторевертимперсонатион:: Кауторевертимперсонатион](#cautorevertimpersonation)|`CAutoRevertImpersonation` Конструирует объект|
|[Кауторевертимперсонатион:: ~ Кауторевертимперсонатион](#dtor)|Уничтожает объект и отменяет олицетворение маркера доступа.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кауторевертимперсонатион:: Attach](#attach)|Автоматизирует переверсию маркера доступа для олицетворения.|
|[Кауторевертимперсонатион::D етач](#detach)|Отмена автоматической переверсии олицетворения.|
|[Кауторевертимперсонатион:: GetAccessToken](#getaccesstoken)|Извлекает маркер доступа Current, связанный с данным объектом.|

## <a name="remarks"></a>Примечания

[Маркер доступа](/windows/win32/SecAuthZ/access-tokens) — это объект, описывающий контекст безопасности процесса или потока, который выделяется каждому пользователю, вошедшему в систему Windows NT или Windows 2000. Эти маркеры доступа можно представить с помощью `CAccessToken` класса.

Иногда требуется олицетворять маркеры доступа. Этот класс предоставляется для удобства, но не выполняет олицетворение маркеров доступа. Он выполняет только автоматическую переверсию до состояния без олицетворения. Это связано с тем, что олицетворение доступа к маркеру может выполняться несколькими разными способами.

Общие сведения о модели управления доступом в Windows см. в разделе [Управление доступом](/windows/win32/SecAuthZ/access-control) в Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** атлсекурити. h

##  <a name="attach"></a>Кауторевертимперсонатион:: Attach

Автоматизирует переверсию маркера доступа для олицетворения.

```
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Параметры

*pAT*<br/>
Адрес объекта [CAccessToken](../../atl/reference/caccesstoken-class.md) для автоматического изменения

### <a name="remarks"></a>Примечания

Этот метод следует использовать, только если объект [кауторевертимперсонатион](../../atl/reference/cautorevertimpersonation-class.md) был создан с пустым `CAccessToken` указателем или если метод [Detach](#detach) был вызван ранее. В простых случаях использовать этот метод необязательно.

##  <a name="cautorevertimpersonation"></a>Кауторевертимперсонатион:: Кауторевертимперсонатион

Создает объект `CAutoRevertImpersonation`.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Параметры

*pAT*<br/>
Адрес объекта [CAccessToken](../../atl/reference/caccesstoken-class.md) для автоматического изменения.

### <a name="remarks"></a>Примечания

Фактическое олицетворение маркера доступа следует выполнять отдельно от и, прежде чем создавать `CAutoRevertImpersonation` объект. Это олицетворение будет восстановлено автоматически, когда `CAutoRevertImpersonation` объект выходит из области действия.

##  <a name="dtor"></a>Кауторевертимперсонатион:: ~ Кауторевертимперсонатион

Уничтожает объект и отменяет олицетворение маркера доступа.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Примечания

Отменяет все олицетворения, действующие в данный момент для объекта [CAccessToken](../../atl/reference/caccesstoken-class.md) , предоставленного либо при конструировании, либо с помощью метода [attach](#attach) . `CAccessToken` Если не связан, деструктор не оказывает никакого влияния.

##  <a name="detach"></a>Кауторевертимперсонатион::D етач

Отмена автоматической переверсии олицетворения.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес ранее связанного [CAccessToken](../../atl/reference/caccesstoken-class.md)или значение null, если ассоциация не существовала.

### <a name="remarks"></a>Примечания

При вызове Detach `CAutoRevertImpersonation` объект не сможет отменить олицетворение, действующее в данный момент для объекта [CAccessToken](../../atl/reference/caccesstoken-class.md) , связанного с этим объектом. `CAutoRevertImpersonation`Затем можно уничтожить без влияния или повторно связать с тем же или с другим `CAccessToken` объектом с помощью [attach](#attach).

##  <a name="getaccesstoken"></a>Кауторевертимперсонатион:: GetAccessToken

Извлекает маркер доступа Current, связанный с данным объектом.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес ранее связанного [CAccessToken](../../atl/reference/caccesstoken-class.md)или значение null, если ассоциация не существовала.

### <a name="remarks"></a>Примечания

Если этот метод вызывается для целей, включающих переверсию олицетворения `CAccessToken` объекта, вместо нее следует использовать метод [Detach](#detach) .

## <a name="see-also"></a>См. также

[Пример Атлсекурити](../../overview/visual-cpp-samples.md)<br/>
[Маркеры доступа](/windows/win32/SecAuthZ/access-tokens)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
