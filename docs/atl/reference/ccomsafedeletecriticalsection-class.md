---
title: Класс Ккомсафеделетекритикалсектион
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
ms.openlocfilehash: da83bc5d0c2ebb79aee07f30069144368169fc26
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821653"
---
# <a name="ccomsafedeletecriticalsection-class"></a>Класс Ккомсафеделетекритикалсектион

Этот класс предоставляет методы для получения и освобождения владения объектом критической секции.

## <a name="syntax"></a>Синтаксис

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Name|Описание|
|----------|-----------------|
|[Ккомсафеделетекритикалсектион:: Ккомсафеделетекритикалсектион](#ccomsafedeletecriticalsection)|Конструктор.|
|[Ккомсафеделетекритикалсектион:: ~ Ккомсафеделетекритикалсектион](#dtor)|Деструктор|

### <a name="public-methods"></a>Общедоступные методы

|Name|Описание|
|----------|-----------------|
|[Ккомсафеделетекритикалсектион:: init](#init)|Создает и инициализирует объект критической секции.|
|[Ккомсафеделетекритикалсектион:: Lock](#lock)|Получает владение объектом критической секции.|
|[Ккомсафеделетекритикалсектион:: Term](#term)|Освобождает системные ресурсы, используемые объектом критического раздела.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_bInitialized](#m_binitialized)|Помечает, инициализирован ли внутренний объект `CRITICAL_SECTION`.|

## <a name="remarks"></a>Заметки

`CComSafeDeleteCriticalSection` является производным от класса [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md). Однако `CComSafeDeleteCriticalSection` предоставляет дополнительные механизмы безопасности по сравнению с [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md).

Когда экземпляр `CComSafeDeleteCriticalSection` выходит из области или явно удаляется из памяти, базовый объект критической секции автоматически очищается, если он по-прежнему является допустимым. Кроме того, метод [ккомсафеделетекритикалсектион:: Term](#term) будет закрыт, если базовый объект критического раздела еще не был выделен или уже освобожден из памяти.

Дополнительные сведения о вспомогательных классах критической секции см. в разделе [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md) .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** атлкоре. h

##  <a name="ccomsafedeletecriticalsection"></a>Ккомсафеделетекритикалсектион:: Ккомсафеделетекритикалсектион

Конструктор.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>Заметки

Задает для элемента данных [m_bInitialized](#m_binitialized) значение false.

##  <a name="dtor"></a>Ккомсафеделетекритикалсектион:: ~ Ккомсафеделетекритикалсектион

Деструктор

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>Заметки

Освобождает внутренний объект `CRITICAL_SECTION` из памяти, если [m_bInitialized](#m_binitialized) элемент данных имеет значение true.

##  <a name="init"></a>Ккомсафеделетекритикалсектион:: init

Вызывает реализацию метода [init](/visualstudio/debugger/init) для базового класса и задает для [m_bInitialized](#m_binitialized) значение true в случае успеха.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [ккомкритикалсектион:: init](../../atl/reference/ccomcriticalsection-class.md#init).

##  <a name="lock"></a>Ккомсафеделетекритикалсектион:: Lock

Вызывает реализацию [блокировки](ccomcriticalsection-class.md#lock)базового класса.

```
HRESULT Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [ккомкритикалсектион:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

### <a name="remarks"></a>Заметки

Этот метод предполагает, что при записи для элемента данных [m_bInitialized](#m_binitialized) ЗАДАНО значение true. Утверждение создается в отладочных сборках, если это условие не выполнено.

Дополнительные сведения о поведении функции см. в разделе [ккомкритикалсектион:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

##  <a name="m_binitialized"></a>Ккомсафеделетекритикалсектион:: m_bInitialized

Помечает, инициализирован ли внутренний объект `CRITICAL_SECTION`.

```
bool m_bInitialized;
```

### <a name="remarks"></a>Заметки

Элемент данных `m_bInitialized` используется для контроля допустимости базового `CRITICAL_SECTION` объекта, связанного с классом [ккомсафеделетекритикалсектион](../../atl/reference/ccomsafedeletecriticalsection-class.md) . Базовый объект `CRITICAL_SECTION` не будет пытаться освободить из памяти, если этот флаг не установлен в значение TRUE.

##  <a name="term"></a>Ккомсафеделетекритикалсектион:: Term

Вызывает реализацию базового класса [ккомкритикалсектион:: Term](../../atl/reference/ccomcriticalsection-class.md#term) , если внутренний объект `CRITICAL_SECTION` является допустимым.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [ккомкритикалсектион:: Term](../../atl/reference/ccomcriticalsection-class.md#term)или S_OK, если для [m_bInitialized](#m_binitialized) было задано значение false при входе.

### <a name="remarks"></a>Заметки

Вызывать этот метод можно, даже если внутренний объект `CRITICAL_SECTION` является недопустимым. Деструктор этого класса вызывает этот метод, если элемент данных [m_bInitialized](#m_binitialized) имеет значение true.

## <a name="see-also"></a>См. также:

[Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
