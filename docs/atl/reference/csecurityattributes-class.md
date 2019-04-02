---
title: Класс CSecurityAttributes
ms.date: 11/04/2016
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
ms.openlocfilehash: 66188a2c944379cfae813220937ac1e7e98fb41d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768345"
---
# <a name="csecurityattributes-class"></a>Класс CSecurityAttributes

Этот класс является тонкой оболочкой для структуры атрибуты безопасности.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CSecurityAttributes::Set](#set)|Вызовите этот метод для задания атрибутов `CSecurityAttributes` объекта.|

## <a name="remarks"></a>Примечания

`SECURITY_ATTRIBUTES` Структура содержит [дескриптор безопасности](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) используется для создания объекта и указывает, наследуется ли дескриптор, полученный путем указания этой структуры.

Введение в модель управления доступом в Windows, см. в разделе [контроля доступа](/windows/desktop/SecAuthZ/access-control) в пакете Windows SDK.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes

Конструктор.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>Параметры

*rSecurityDescriptor*<br/>
Ссылка на дескриптор безопасности.

*bInheritsHandle*<br/>
Определяет, наследуется ли возвращаемый дескриптор при создании процесса. Если этот элемент имеет значение true, новый процесс наследует дескриптор.

##  <a name="set"></a>  CSecurityAttributes::Set

Вызовите этот метод для задания атрибутов `CSecurityAttributes` объекта.

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Параметры

*rSecurityDescriptor*<br/>
Ссылка на дескриптор безопасности.

*bInheritHandle*<br/>
Определяет, наследуется ли возвращаемый дескриптор при создании процесса. Если этот элемент имеет значение true, новый процесс наследует дескриптор.

### <a name="remarks"></a>Примечания

Этот метод используется конструктором для инициализации `CSecurityAttributes` объекта.

## <a name="see-also"></a>См. также

[Образец безопасности](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)<br/>
[Дескриптор безопасности](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
