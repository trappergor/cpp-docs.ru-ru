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
ms.openlocfilehash: 113bcebb7461415590156206ee7aa4c91e0e93d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330987"
---
# <a name="csecurityattributes-class"></a>Класс CSecurityAttributes

Этот класс представляет собой тонкую обертку для структуры атрибутов безопасности.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSecurityAttributes::Set](#set)|Вызовите этот метод, чтобы `CSecurityAttributes` установить атрибуты объекта.|

## <a name="remarks"></a>Remarks

Структура `SECURITY_ATTRIBUTES` содержит [дескриптор безопасности,](/windows/win32/api/winnt/ns-winnt-security_descriptor) используемый для создания объекта, и определяет, является ли извлеченная ручка науказной, указав эту структуру, наследуемой.

Для введения в модель управления доступом [Access Control](/windows/win32/SecAuthZ/access-control) в Windows см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Требования

**Заголовок:** atlsecurity.h

## <a name="csecurityattributescsecurityattributes"></a><a name="csecurityattributes"></a>CSecurityAttributes::CSecurityAttributes

Конструктор.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>Параметры

*rSecurityДескриптор*<br/>
Ссылка на дескриптор безопасности.

*bНаследыРучка*<br/>
Определяет, наследуется ли возвращаемый дескриптор при создании процесса. Если этот элемент имеет значение true, новый процесс наследует дескриптор.

## <a name="csecurityattributesset"></a><a name="set"></a>CSecurityAttributes::Set

Вызовите этот метод, чтобы `CSecurityAttributes` установить атрибуты объекта.

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Параметры

*rSecurityДескриптор*<br/>
Ссылка на дескриптор безопасности.

*bНаследыХи*<br/>
Определяет, наследуется ли возвращаемый дескриптор при создании процесса. Если этот элемент имеет значение true, новый процесс наследует дескриптор.

### <a name="remarks"></a>Remarks

Этот метод используется конструктором для инициализации `CSecurityAttributes` объекта.

## <a name="see-also"></a>См. также раздел

[Пример безопасности](../../overview/visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))<br/>
[дескриптор безопасности](/windows/win32/api/winnt/ns-winnt-security_descriptor)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Глобальные функции безопасности](../../atl/reference/security-global-functions.md)
