---
title: Класс HStringReference
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::Get
- corewrappers/Microsoft::WRL::Wrappers::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HStringReference class
- Microsoft::WRL::Wrappers::HStringReference::CopyTo method
- Microsoft::WRL::Wrappers::HStringReference::Get method
- Microsoft::WRL::Wrappers::HStringReference::HStringReference, constructor
- Microsoft::WRL::Wrappers::HStringReference::operator= operator
- Microsoft::WRL::Wrappers::HStringReference::operator== operator
- Microsoft::WRL::Wrappers::HStringReference::operator!= operator
- Microsoft::WRL::Wrappers::HStringReference::operator< operator
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
ms.openlocfilehash: fd064f97081fad1a9df9de0865bb7c46ad5b4484
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371424"
---
# <a name="hstringreference-class"></a>Класс HStringReference

Представляет HSTRING, созданный из существующей строки.

## <a name="syntax"></a>Синтаксис

```cpp
class HStringReference;
```

## <a name="remarks"></a>Remarks

Срок службы резервного буфера в новом HSTRING не управляется Windows Runtime. Вызывающее распределение строки исходного кода на кадре стека, чтобы избежать распределения кучи и устранить риск утечки памяти. Кроме того, вызываец должен убедиться, что строка исходного кода остается неизменной в течение всего срока службы прикрепленного HSTRING. Для получения дополнительной [WindowsCreateStringReference function](/windows/win32/api/winstring/nf-winstring-windowscreatestringreference)информации см.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                    | Описание
------------------------------------------------------- | -----------------------------------------------------------
[HStringСправка:HStringСправка](#hstringreference) | Инициализирует новый экземпляр класса `HStringReference`.

### <a name="public-methods"></a>Открытые методы

Участник                              | Описание
----------------------------------- | ------------------------------------------------------------------
[HStringReference::CopyTo](#copyto) | Копирует текущий `HStringReference` объект с объектом HSTRING.
[HStringСправка::Получить](#get)       | Получает значение основной ручки HSTRING.
[HStringСправка::GetRawBuffer](#getrawbuffer) | Извлекает указатель на базовые строки данных.

### <a name="public-operators"></a>Открытые операторы

Имя                                                  | Описание
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[HStringСправка::оператор](#operator-assign)       | Перемещает значение другого `HStringReference` объекта `HStringReference` к текущему объекту.
[HStringСправка::оператор](#operator-equality)    | Указывает, являются ли эти два параметра равными.
[HStringСправка::оператор!](#operator-inequality)  | Указывает, не являются ли эти два параметра равными.
[HStringСправка:Оператор&lt;](#operator-less-than) | Указывает, является ли первый параметр меньше второго параметра.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HStringReference`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Wrappers

## <a name="hstringreferencecopyto"></a><a name="copyto"></a>HStringСправка::CopyTo

Копирует текущий `HStringReference` объект с объектом HSTRING.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
HSTRING, который получает копию.

### <a name="remarks"></a>Remarks

Этот метод вызывает функцию [WindowsDuplicateString.](/windows/win32/api/winstring/nf-winstring-windowsduplicatestring)

## <a name="hstringreferenceget"></a><a name="get"></a>HStringСправка::Получить

Получает значение основной ручки HSTRING.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Возвращаемое значение

Значение базового дескриптора HSTRING.

## <a name="hstringreferencegetrawbuffer"></a><a name="getrawbuffer"></a>HStringСправка::GetRawBuffer

Извлекает указатель на базовые строки данных.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>Параметры

*длина* Указатель на переменную **int,** которая получает длину данных.

### <a name="return-value"></a>Возвращаемое значение

**Конст** указатель на базовые строки данных.

## <a name="hstringreferencehstringreference"></a><a name="hstringreference"></a>HStringСправка:HStringСправка

Инициализирует новый экземпляр класса `HStringReference`.

```cpp
template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest]) throw();

template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest],
                 unsigned int len) throw();

HStringReference(HStringReference&& other) throw();
```

### <a name="parameters"></a>Параметры

*размерDest*<br/>
Параметр шаблона, опознавательный размер буфера назначения. `HStringReference`

*Ул*<br/>
Ссылка на строку широкого характера.

*Лен*<br/>
Максимальная длина буфера параметра *str* для использования в этой операции. Если параметр *len* не указан, используется весь параметр *str.* Если *лен* больше, чем *размерDest,* *len* установлен на *размерDest*-1.

*Других*<br/>
Другой `HStringReference` объект.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует новый `HStringReference` объект того же размера, что и параметр *str.*

Второй конструктор инициализирует новый `HStringReference` объект, размер specifeid по параметру *len.*

Третий конструктор инициализирует новый `HStringReference` объект со значением *другого* параметра, а затем уничтожает *другой* параметр.

## <a name="hstringreferenceoperator"></a><a name="operator-assign"></a>HStringСправка::оператор

Перемещает значение другого `HStringReference` объекта `HStringReference` к текущему объекту.

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Существующий объект `HStringReference`.

### <a name="remarks"></a>Remarks

Значение существующего *другого* объекта скопировано на текущий `HStringReference` объект, а затем *другой* объект разрушается.

## <a name="hstringreferenceoperator"></a><a name="operator-equality"></a>HStringСправка::оператор

Указывает, являются ли эти два параметра равными.

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
Первый параметр для сравнения. *lHS* может `HStringReference` быть объектом или ручкой HSTRING.

*rhs*<br/>
Второй параметр для сравнения.  *rhs* может `HStringReference` быть объектом или ручкой HSTRING.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параметры *lhs* и *rhs* равны; в противном случае, **ложные**.

## <a name="hstringreferenceoperator"></a><a name="operator-inequality"></a>HStringСправка::оператор!

Указывает, не являются ли эти два параметра равными.

```cpp
inline bool operator!=(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
Первый параметр для сравнения. *lHS* может `HStringReference` быть объектом или ручкой HSTRING.

*rhs*<br/>
Второй параметр для сравнения.  *rhs* может `HStringReference` быть объектом или ручкой HSTRING.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параметры *lhs* и *rhs* не равны; в противном случае, **ложные**.

## <a name="hstringreferenceoperatorlt"></a><a name="operator-less-than"></a>HStringСправка:Оператор&lt;

Указывает, является ли первый параметр меньше второго параметра.

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
Первый параметр для сравнения. *lhs* может быть ссылкой на `HStringReference`.

*rhs*<br/>
Второй параметр для сравнения.  *rhs* может быть ссылкой на `HStringReference`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параметр *lhs* меньше параметра *rhs;* в противном случае, **ложные**.
