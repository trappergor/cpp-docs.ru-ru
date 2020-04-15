---
title: CComSafeDeleteCriticalSection класс
ms.date: 11/04/2016
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
ms.openlocfilehash: cb0dc440fc0e79e0023b5fbd6e4ca2345d031d3d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327369"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection класс

Этот класс предоставляет методы получения и освобождения права собственности на объект критического раздела.

## <a name="syntax"></a>Синтаксис

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::CComSafeDeletecriticalSection](#ccomsafedeletecriticalsection)|Конструктор.|
|[CComSafeDeleteCriticalSection:: »CComSafeDeletecriticalSection](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::Init](#init)|Создает и инициализирует критический объект раздела.|
|[CComSafeDeleteCriticalSection::Lock](#lock)|Получает право собственности на объект критического сечения.|
|[CComSafeDeleteCriticalSection::Срок](#term)|Выпускает системные ресурсы, используемые критическим объектом секции.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_bInitialized](#m_binitialized)|Флаги ли `CRITICAL_SECTION` внутренний объект был инициализирован.|

## <a name="remarks"></a>Remarks

`CComSafeDeleteCriticalSection`вытекает из класса [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Тем `CComSafeDeleteCriticalSection` не менее, обеспечивает дополнительные механизмы безопасности над [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).

Когда экземпляр `CComSafeDeleteCriticalSection` выходит из области или явно удаляется из памяти, основной объект критического раздела автоматически очищается, если он по-прежнему действителен. Кроме того, [CComSafeDeleteCriticalSection::Термин](#term) метод выйдет изящно, если основной объект критического сечения еще не выделен или уже освобожден из памяти.

Дополнительную информацию о критических классах помощников секции можно узнать на [cComCriticalSection.](../../atl/reference/ccomcriticalsection-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** atlcore.h

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a>CComSafeDeleteCriticalSection::CComSafeDeletecriticalSection

Конструктор.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>Remarks

Устанавливает m_bInitialized член [данных](#m_binitialized) в FALSE.

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a>CComSafeDeleteCriticalSection:: »CComSafeDeletecriticalSection

Деструктор

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>Remarks

Освобождает внутренний `CRITICAL_SECTION` объект из памяти, [m_bInitialized](#m_binitialized) если m_bInitialized данный настроен на ИСТИНу.

## <a name="ccomsafedeletecriticalsectioninit"></a><a name="init"></a>CComSafeDeleteCriticalSection::Init

Вызывает реализацию базового класса [Init](/visualstudio/debugger/init) и устанавливает [m_bInitialized](#m_binitialized) к TRUE в случае успеха.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init).

## <a name="ccomsafedeletecriticalsectionlock"></a><a name="lock"></a>CComSafeDeleteCriticalSection::Lock

Вызывает реализацию [базового](ccomcriticalsection-class.md#lock)класса Lock .

```
HRESULT Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

### <a name="remarks"></a>Remarks

Этот метод предполагает, [что m_bInitialized](#m_binitialized) данных член установлен на TRUE при входе. Утверждение генерируется в сборках Debug, если это условие не выполнено.

Для получения дополнительной информации о поведении функции, обратитесь к [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

## <a name="ccomsafedeletecriticalsectionm_binitialized"></a><a name="m_binitialized"></a>CComSafeDeleteCriticalSection::m_bInitialized

Флаги ли `CRITICAL_SECTION` внутренний объект был инициализирован.

```
bool m_bInitialized;
```

### <a name="remarks"></a>Remarks

Член `m_bInitialized` данных используется для отслеживания достоверности базового `CRITICAL_SECTION` объекта, связанного с классом [CComSafeDeleteCriticalSection.](../../atl/reference/ccomsafedeletecriticalsection-class.md) Основной `CRITICAL_SECTION` объект не будет предпринят, если этот флаг не будет установлен на ИСТИНу.

## <a name="ccomsafedeletecriticalsectionterm"></a><a name="term"></a>CComSafeDeleteCriticalSection::Срок

Вызывает реализацию базового класса [CComCriticalSection::Term,](../../atl/reference/ccomcriticalsection-class.md#term) если внутренний `CRITICAL_SECTION` объект действителен.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [CComCriticalSection::Срок](../../atl/reference/ccomcriticalsection-class.md#term), или S_OK, если [m_bInitialized](#m_binitialized) был установлен на FALSE при входе.

### <a name="remarks"></a>Remarks

Этот метод можно назвать безопасным, `CRITICAL_SECTION` даже если внутренний объект недействителен. Деструктор этого класса вызывает этот [метод,](#m_binitialized) если m_bInitialized данный член установлен в TRUE.

## <a name="see-also"></a>См. также раздел

[Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
