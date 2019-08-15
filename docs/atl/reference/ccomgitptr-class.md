---
title: Класс Ккомгитптр
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
ms.openlocfilehash: 00265cc445191a5a539ab21d6f64b255849495e9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497261"
---
# <a name="ccomgitptr-class"></a>Класс Ккомгитптр

Этот класс предоставляет методы для работы с указателями интерфейса и глобальной таблицей интерфейса (GIT).

## <a name="syntax"></a>Синтаксис

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя интерфейса, который должен храниться в GIT.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ккомгитптр:: Ккомгитптр](#ccomgitptr)|Конструктор.|
|[Ккомгитптр:: ~ Ккомгитптр](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккомгитптр:: Attach](#attach)|Вызовите этот метод, чтобы зарегистрировать указатель интерфейса в глобальной таблице интерфейса (GIT).|
|[Ккомгитптр:: CopyTo](#copyto)|Вызовите этот метод, чтобы скопировать интерфейс из глобальной таблицы интерфейса (GIT) в переданный указатель.|
|[Ккомгитптр::D етач](#detach)|Вызовите этот метод, чтобы разорвать связь интерфейса `CComGITPtr` с объектом.|
|[Ккомгитптр:: Кука](#getcookie)|Вызовите этот метод, чтобы вернуть куки- `CComGITPtr` файл из объекта.|
|[Ккомгитптр:: REVOKE](#revoke)|Вызовите этот метод, чтобы удалить интерфейс из глобальной таблицы интерфейса (GIT).|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Ккомгитптр:: operator DWORD](#operator_dword)|Возвращает файл cookie из `CComGITPtr` объекта.|
|[Ккомгитптр:: operator =](#operator_eq)|Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Ккомгитптр:: m_dwCookie](#m_dwcookie)|Файл cookie.|

## <a name="remarks"></a>Примечания

Объекты, объединяющие Свободный потоковый маршалером и требующие использования указателей интерфейса, полученных из других объектов, должны предпринимать дополнительные действия, чтобы обеспечить правильную упаковку интерфейсов. Обычно это подразумевает сохранение указателей интерфейса в GIT и получение указателя из GIT при каждом его использовании. Класс `CComGITPtr` предоставляется для помощи в использовании указателей интерфейса, хранящихся в Git.

> [!NOTE]
>  Средство глобального интерфейса таблицы доступно только в Windows 95 с DCOM версии 1,1 и более поздних версий, Windows 98, Windows NT 4,0 с пакетом обновления 3 и более поздней версии и Windows 2000.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

##  <a name="attach"></a>Ккомгитптр:: Attach

Вызовите этот метод, чтобы зарегистрировать указатель интерфейса в глобальной таблице интерфейса (GIT).

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>Параметры

*p*<br/>
Указатель интерфейса, добавляемый в GIT.

*двкукие*<br/>
Файл cookie, используемый для распознавания указателя интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

В отладочных сборках возникнет ошибка утверждения, если GIT является недопустимым или если файл cookie равен NULL.

##  <a name="ccomgitptr"></a>Ккомгитптр:: Ккомгитптр

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
окне Указатель интерфейса, который должен храниться в глобальной таблице интерфейса (GIT).

*Git*<br/>
окне Ссылка на существующий `CComGITPtr` объект.

*двкукие*<br/>
окне Файл cookie, используемый для распознавания указателя интерфейса.

*RV*<br/>
окне Исходный `CComGITPtr` объект, из которого нужно переместить данные.

### <a name="remarks"></a>Примечания

Создает новый `CComGITPtr` объект, при необходимости используя существующий `CComGITPtr` объект.

Конструктор, использующий *RV* , является конструктором перемещения. Данные перемещаются из источника, *RV*, а затем *RV* очищаются.

##  <a name="dtor"></a>Ккомгитптр:: ~ Ккомгитптр

Деструктор

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>Примечания

Удаляет интерфейс из глобальной таблицы интерфейса (GIT) с помощью [ккомгитптр:: REVOKE](#revoke).

##  <a name="copyto"></a>Ккомгитптр:: CopyTo

Вызовите этот метод, чтобы скопировать интерфейс из глобальной таблицы интерфейса (GIT) в переданный указатель.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>Параметры

*PP*<br/>
Указатель, который должен получить интерфейс.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Интерфейс из GIT копируется в переданный указатель. Указатель должен быть освобожден вызывающим объектом, если он больше не требуется.

##  <a name="detach"></a>Ккомгитптр::D етач

Вызовите этот метод, чтобы разорвать связь интерфейса `CComGITPtr` с объектом.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает файл cookie из `CComGITPtr` объекта.

### <a name="remarks"></a>Примечания

Вызывающий объект удаляет интерфейс из GIT с помощью [ккомгитптр:: REVOKE](#revoke).

##  <a name="getcookie"></a>Ккомгитптр:: Кука

Вызовите этот метод, чтобы вернуть куки- `CComGITPtr` файл из объекта.

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает файл cookie.

### <a name="remarks"></a>Примечания

Файл cookie — это переменная, используемая для определения интерфейса и его расположения.

##  <a name="m_dwcookie"></a>Ккомгитптр:: m_dwCookie

Файл cookie.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>Примечания

Файл cookie — это переменная-член, используемая для определения интерфейса и его расположения.

##  <a name="operator_eq"></a>Ккомгитптр:: operator =

Оператор присваивания.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>Параметры

*p*<br/>
окне Указатель на интерфейс.

*Git*<br/>
[in] Ссылка на объект `CComGITPtr`.

*двкукие*<br/>
окне Файл cookie, используемый для распознавания указателя интерфейса.

*RV*<br/>
окне Объект `CComGITPtr` , из которого нужно переместить данные.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComGITPtr` объект.

### <a name="remarks"></a>Примечания

Присваивает новое значение `CComGITPtr` объекту либо из существующего объекта, либо из ссылки на глобальную таблицу интерфейса.

##  <a name="operator_dword"></a>Ккомгитптр:: operator DWORD

Возвращает файл cookie, связанный с `CComGITPtr` объектом.

```
operator DWORD() const;
```

### <a name="remarks"></a>Примечания

Файл cookie — это переменная, используемая для определения интерфейса и его расположения.

##  <a name="revoke"></a>Ккомгитптр:: REVOKE

Вызовите этот метод, чтобы удалить текущий интерфейс из глобальной таблицы интерфейса (GIT).

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Удаляет интерфейс из GIT.

## <a name="see-also"></a>См. также

[Свободный потоковый маршалеру](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[Доступ к интерфейсам в разных апартаментах](/windows/win32/com/accessing-interfaces-across-apartments)<br/>
[Когда следует использовать глобальную таблицу интерфейса](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
