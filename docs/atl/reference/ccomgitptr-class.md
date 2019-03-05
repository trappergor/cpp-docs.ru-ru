---
title: Класс CComGITPtr
ms.date: 11/04/2016
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
ms.openlocfilehash: bf509d027833610e4251c009d4e444dad3fdd5ce
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296037"
---
# <a name="ccomgitptr-class"></a>Класс CComGITPtr

Этот класс предоставляет методы для обработки указателей интерфейса и глобальной таблицы интерфейсов (GIT).

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя интерфейса для сохранения в GIT.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Конструктор.|
|[CComGITPtr::~CComGITPtr](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CComGITPtr::Attach](#attach)|Этот метод используется для регистрации указателя интерфейса в глобальной таблицы интерфейсов (GIT).|
|[CComGITPtr::CopyTo](#copyto)|Этот метод используется для копирования интерфейс из глобальной таблицы интерфейсов (GIT) в переданных указатель.|
|[CComGITPtr::Detach](#detach)|Вызовите этот метод, чтобы отделить интерфейс из `CComGITPtr` объекта.|
|[CComGITPtr::GetCookie](#getcookie)|Вызовите этот метод, чтобы вернуть файл cookie из `CComGITPtr` объекта.|
|[CComGITPtr::Revoke](#revoke)|Вызовите этот метод, чтобы удалить интерфейс из глобальной таблицы интерфейсов (GIT).|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CComGITPtr::operator DWORD](#operator_dword)|Возвращает файл cookie из `CComGITPtr` объекта.|
|[CComGITPtr::operator =](#operator_eq)|Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComGITPtr::m_dwCookie](#m_dwcookie)|Файл cookie.|

## <a name="remarks"></a>Примечания

Объекты, которые статистическая обработка свободного упаковщик и должны использовать указатели интерфейса получен из других объектов должны предпринять дополнительные действия, чтобы убедиться, что интерфейсы маршалируются правильно. Как правило, это подразумевает хранение указателе на интерфейс в GIT и получение указателя из GIT каждый раз, когда он используется. Класс `CComGITPtr` помогут вам использовать указатели на интерфейс, хранящиеся в GIT.

> [!NOTE]
>  Средство таблицы общий интерфейс доступен только в Windows 95 с DCOM версии 1.1 и более поздней версии, Windows 98, Windows NT 4.0 с пакетом обновления 3 и более поздних версий и Windows 2000.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

##  <a name="attach"></a>  CComGITPtr::Attach

Этот метод используется для регистрации указателя интерфейса в глобальной таблицы интерфейсов (GIT).

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель на интерфейс, добавляемых к GIT.

*dwCookie*<br/>
Файл cookie, используемый для идентификации указатель интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

В отладочных сборках произойдет ошибка утверждения, если GIT не является допустимым, или если файл cookie равен NULL.

##  <a name="ccomgitptr"></a>  CComGITPtr::CComGITPtr

Конструктор.

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>Параметры

*p*<br/>
[in] Указатель интерфейса, для сохранения в глобальной таблицы интерфейсов (GIT).

*Git*<br/>
[in] Ссылка на существующий `CComGITPtr` объекта.

*dwCookie*<br/>
[in] Файл cookie, используемый для идентификации указатель интерфейса.

*rv*<br/>
[in] Источник `CComGITPtr` объект для перемещения данных.

### <a name="remarks"></a>Примечания

Создает новый `CComGITPtr` объекта, при необходимости с помощью существующего `CComGITPtr` объекта.

Использование конструктора *rv* является конструктором перемещения. При перемещении данных из источника, *rv*, а затем *rv* очищается.

##  <a name="dtor"></a>  CComGITPtr::~CComGITPtr

Деструктор

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>Примечания

Удаляет интерфейс из глобальной таблицы интерфейсов (GIT), с помощью [CComGITPtr::Revoke](#revoke).

##  <a name="copyto"></a>  CComGITPtr::CopyTo

Этот метод используется для копирования интерфейс из глобальной таблицы интерфейсов (GIT) в переданных указатель.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>Параметры

*PP*<br/>
Указатель, который должен получать интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Указатель, переданный копируется в интерфейс из GIT. Указатель должны быть освобождены вызывающим объектом, когда он больше не требуется.

##  <a name="detach"></a>  CComGITPtr::Detach

Вызовите этот метод, чтобы отделить интерфейс из `CComGITPtr` объекта.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает файл cookie из `CComGITPtr` объекта.

### <a name="remarks"></a>Примечания

Это вызывающий объект должен удалить интерфейс из GIT, с помощью [CComGITPtr::Revoke](#revoke).

##  <a name="getcookie"></a>  CComGITPtr::GetCookie

Вызовите этот метод, чтобы вернуть файл cookie из `CComGITPtr` объекта.

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает файл cookie.

### <a name="remarks"></a>Примечания

Файл cookie является переменная, используемая для идентификации интерфейса и его расположение.

##  <a name="m_dwcookie"></a>  CComGITPtr::m_dwCookie

Файл cookie.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>Примечания

Файл cookie является переменной-члена, используемый для идентификации интерфейса и его расположение.

##  <a name="operator_eq"></a>  CComGITPtr::operator =

Оператор присваивания.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>Параметры

*p*<br/>
[in] Указатель на интерфейс.

*Git*<br/>
[in] Ссылка на объект `CComGITPtr`.

*dwCookie*<br/>
[in] Файл cookie, используемый для идентификации указатель интерфейса.

*rv*<br/>
[in] `CComGITPtr` Для перемещения данных из.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComGITPtr` объекта.

### <a name="remarks"></a>Примечания

Назначает новое значение для `CComGITPtr` объекта, из существующего объекта или из ссылки на общую таблицу интерфейса.

##  <a name="operator_dword"></a>  CComGITPtr::operator DWORD

Возвращает файл cookie, связанный с `CComGITPtr` объекта.

```
operator DWORD() const;
```

### <a name="remarks"></a>Примечания

Файл cookie является переменная, используемая для идентификации интерфейса и его расположение.

##  <a name="revoke"></a>  CComGITPtr::Revoke

Вызовите этот метод, чтобы удалить текущий интерфейс из глобальной таблицы интерфейсов (GIT).

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="remarks"></a>Примечания

Удаляет интерфейс из GIT.

## <a name="see-also"></a>См. также

[Упаковщик в режиме свободного](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[Доступ к интерфейсам между подразделениями](/windows/desktop/com/accessing-interfaces-across-apartments)<br/>
[Когда следует использовать глобальной таблицы интерфейсов](/windows/desktop/com/when-to-use-the-global-interface-table)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
