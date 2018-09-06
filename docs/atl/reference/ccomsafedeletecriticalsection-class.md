---
title: Класс CComSafeDeleteCriticalSection | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
dev_langs:
- C++
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ea024475f824745ac8f99a957b5a75f9f4db22c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754801"
---
# <a name="ccomsafedeletecriticalsection-class"></a>Класс CComSafeDeleteCriticalSection

Этот класс предоставляет методы для получения и освобождения владения объект критической секции.

## <a name="syntax"></a>Синтаксис

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|Конструктор.|
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::Init](#init)|Создает и инициализирует объект критической секции.|
|[CComSafeDeleteCriticalSection::Lock](#lock)|Получает права владельца объекта критической секции.|
|[CComSafeDeleteCriticalSection::Term](#term)|Освобождает системные ресурсы, используемые объектом критический раздел.|

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_bInitialized](#m_binitialized)|Флаги ли внутренний `CRITICAL_SECTION` объект был инициализирован.|

## <a name="remarks"></a>Примечания

`CComSafeDeleteCriticalSection` является производным от класса [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Тем не менее `CComSafeDeleteCriticalSection` предоставляет механизмы дополнительной безопасности через [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).

При создании экземпляра класса `CComSafeDeleteCriticalSection` выходит за пределы области, или явно удаляется из памяти, базовый объект критической секции будут автоматически удалены, если он по-прежнему допустим. Кроме того [CComSafeDeleteCriticalSection::Term](#term) метод завершит свою работу, если базовый объект критический раздел еще не был выделен, или уже был выпущен из памяти.

См. в разделе [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) Дополнительные сведения о вспомогательных классов критический раздел.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** файле atlcore.h

##  <a name="ccomsafedeletecriticalsection"></a>  CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection

Конструктор.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>Примечания

Наборы [m_bInitialized](#m_binitialized) элемент данных в значение FALSE.

##  <a name="dtor"></a>  CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection

Деструктор

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>Примечания

Освобождает внутренний `CRITICAL_SECTION` объект из памяти, если [m_bInitialized](#m_binitialized) члена данных задано значение true.

##  <a name="init"></a>  CComSafeDeleteCriticalSection::Init

Вызывает реализацию базового класса [Init](/visualstudio/debugger/init) и задает [m_bInitialized](#m_binitialized) значение true при успешном выполнении.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init).

##  <a name="lock"></a>  CComSafeDeleteCriticalSection::Lock

Вызывает реализацию базового класса [блокировки](ccomcriticalsection-class.md#lock).  

```
HRESULT Lock();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

### <a name="remarks"></a>Примечания

Этот способ предполагает [m_bInitialized](#m_binitialized) члена данных задано значение true при входе. При несоблюдении этой condidtion, утверждение создается в отладочных сборках.

Дополнительные сведения о работе функции см. [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

##  <a name="m_binitialized"></a>  CComSafeDeleteCriticalSection::m_bInitialized

Флаги ли внутренний `CRITICAL_SECTION` объект был инициализирован.

```
bool m_bInitialized;
```

### <a name="remarks"></a>Примечания

`m_bInitialized` Данные-член используется для отслеживания действия базового `CRITICAL_SECTION` объект, связанный с [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) класса. Базовый `CRITICAL_SECTION` объект не будет предпринята попытка будет освобожден из памяти, если этот флаг не установлен в значение TRUE.

##  <a name="term"></a>  CComSafeDeleteCriticalSection::Term

Вызывает реализацию базового класса [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) если внутренний `CRITICAL_SECTION` объект является допустимым.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает результат [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), или значение s_ок Если [m_bInitialized](#m_binitialized) имел значение FALSE при входе.

### <a name="remarks"></a>Примечания

Это безопасно вызывать этот метод даже в том случае, если внутренний `CRITICAL_SECTION` объект не является допустимым. Деструктор этого класса вызывает этот метод, если [m_bInitialized](#m_binitialized) члена данных задано значение true.

## <a name="see-also"></a>См. также

[Класс CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
