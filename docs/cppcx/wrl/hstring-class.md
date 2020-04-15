---
title: Класс HString
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
- corewrappers/Microsoft::WRL::Wrappers::HString::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
- corewrappers/Microsoft::WRL::Wrappers::HString::Get
- corewrappers/Microsoft::WRL::Wrappers::HString::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
- corewrappers/Microsoft::WRL::Wrappers::HString::Release
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
- corewrappers/Microsoft::WRL::Wrappers::HString::~HString
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HString class
- Microsoft::WRL::Wrappers::HString::Attach method
- Microsoft::WRL::Wrappers::HString::CopyTo method
- Microsoft::WRL::Wrappers::HString::Detach method
- Microsoft::WRL::Wrappers::HString::Get method
- Microsoft::WRL::Wrappers::HString::GetAddressOf method
- Microsoft::WRL::Wrappers::HString::HString, constructor
- Microsoft::WRL::Wrappers::HString::IsValid method
- Microsoft::WRL::Wrappers::HString::MakeReference method
- Microsoft::WRL::Wrappers::HString::operator= operator
- Microsoft::WRL::Wrappers::HString::operator== operator
- Microsoft::WRL::Wrappers::HString::operator!= operator
- Microsoft::WRL::Wrappers::HString::operator< operator
- Microsoft::WRL::Wrappers::HString::Release method
- Microsoft::WRL::Wrappers::HString::Set method
- Microsoft::WRL::Wrappers::HString::~HString, destructor
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
ms.openlocfilehash: 625d7b7d6fc001a6fb63144807b5f29d3620485b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371434"
---
# <a name="hstring-class"></a>Класс HString

Класс помощника для управления сроком службы [HSTRING](/windows/win32/WinRT/hstring) с использованием шаблона RAII.

## <a name="syntax"></a>Синтаксис

```cpp
class HString;
```

## <a name="remarks"></a>Remarks

Windows Runtime обеспечивает доступ к строкам через ручки [HSTRING.](/windows/win32/WinRT/hstring) Класс `HString` обеспечивает удобные функции и операторов для упрощения использования hSTRING ручки. Этот класс может обрабатывать срок службы HSTRING, которым он владеет, с помощью шаблона RAII.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                | Описание
----------------------------------- | -----------------------------------------------------
[HString:HString](#hstring)        | Инициализирует новый экземпляр класса `HString`.
[HString::'HString](#tilde-hstring) | Уничтожает текущий `HString` экземпляр класса.

### <a name="public-methods"></a>Открытые методы

Имя                                     | Описание
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString:Attach](#attach)               | Связывает указанный `HString` объект с `HString` текущим объектом.
[HString::CopyTo](#copyto)               | Копирует текущий `HString` объект с объектом HSTRING.
[HString::Detach](#detach)               | Отсовывает указанный `HString` объект от его базового значения.
[HString::Get](#get)                     | Получает значение основной ручки HSTRING.
[HString::GetAddressOf](#getaddressof)   | Извлекает указатель на основную ручку HSTRING.
[HString::GetRawBuffer](#getrawbuffer)   | Извлекает указатель на базовые строки данных.
[HString:IsValid](#isvalid)             | Указывает, является `HString` ли текущий объект допустимом.
[HString::MakeReference](#makereference) | Создает `HStringReference` объект из заданного параметра строки.
[HString::Release](#release)             | Удаляет базовое значение строки и инциализационирует текущий `HString` объект в пустое значение.
[HString::Установить](#set)                     | Устанавливает значение текущего `HString` объекта к указанной строке или `HString` параметру широкого символа.

### <a name="public-operators"></a>Открытые операторы

Имя                                         | Описание
-------------------------------------------- | ----------------------------------------------------------------------------
[HString::оператор](#operator-assign)       | Перемещает значение другого `HString` объекта `HString` к текущему объекту.
[HString::оператор](#operator-equality)    | Указывает, являются ли эти два параметра равными.
[HString::оператор!](#operator-inequality)  | Указывает, не являются ли эти два параметра равными.
[HString:оператор&lt;](#operator-less-than) | Указывает, является ли первый параметр меньше второго параметра.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HString`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Wrappers

## <a name="hstringhstring"></a><a name="tilde-hstring"></a>HString::'HString

Уничтожает текущий `HString` экземпляр класса.

```cpp
~HString() throw()
```

## <a name="hstringattach"></a><a name="attach"></a>HString:Attach

Связывает указанный `HString` объект с `HString` текущим объектом.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>Параметры

*hstr*<br/>
Существующий объект `HString`.

## <a name="hstringcopyto"></a><a name="copyto"></a>HString::CopyTo

Копирует текущий `HString` объект с объектом HSTRING.

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

## <a name="hstringdetach"></a><a name="detach"></a>HString::Detach

Отсовывает указанный `HString` объект от его базового значения.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Возвращаемое значение

Базовое `HString` значение до начала операции отсоединить.

## <a name="hstringget"></a><a name="get"></a>HString::Get

Получает значение основной ручки HSTRING.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Возвращаемое значение

Значение базового дескриптора HSTRING.

## <a name="hstringgetaddressof"></a><a name="getaddressof"></a>HString::GetAddressOf

Извлекает указатель на основную ручку HSTRING.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовый дескриптор HSTRING.

### <a name="remarks"></a>Remarks

После этой операции строковое значение базового дескриптора HSTRING будет уничтожено.

## <a name="hstringgetrawbuffer"></a><a name="getrawbuffer"></a>HString::GetRawBuffer

Извлекает указатель на базовые строки данных.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```

### <a name="parameters"></a>Параметры

*длина* Указатель на переменную **int,** которая получает длину данных.

### <a name="return-value"></a>Возвращаемое значение

**Конст** указатель на базовые строки данных.

## <a name="hstringhstring"></a><a name="hstring"></a>HString:HString

Инициализирует новый экземпляр класса `HString`.

```cpp
HString() throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>Параметры

*hstr*<br/>
Ручка HSTRING.

*Других*<br/>
Существующий объект `HString`.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует новый `HString` объект, который пуст.

Второй конструктор инициализирует новый `HString` объект со значением существующего *другого* параметра, а затем уничтожает *другой* параметр.

## <a name="hstringisvalid"></a><a name="isvalid"></a>HString:IsValid

Указывает, пуст `HString` текущий объект или нет.

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>Параметры

**верно,** если `HString` текущий объект не пуст; в противном случае, **ложные**.

## <a name="hstringmakereference"></a><a name="makereference"></a>HString::MakeReference

Создает `HStringReference` объект из заданного параметра строки.

```cpp
template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[ sizeDest]);

    template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[sizeDest],
              unsigned int len);
```

### <a name="parameters"></a>Параметры

*размерDest*<br/>
Параметр шаблона, опознавательный размер буфера назначения. `HStringReference`

*Ул*<br/>
Ссылка на строку широкого характера.

*Лен*<br/>
Максимальная длина буфера параметра *str* для использования в этой операции. Если параметр *len* не указан, используется весь параметр *str.*

### <a name="return-value"></a>Возвращаемое значение

Объект, `HStringReference` значение которого такое же, как и указанный параметр *str.*

## <a name="hstringoperator-operator"></a><a name="operator-assign"></a>HString:Оператор оператор

Перемещает значение другого `HString` объекта `HString` к текущему объекту.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Существующий объект `HString`.

### <a name="remarks"></a>Remarks

Значение существующего *другого* объекта скопировано на текущий `HString` объект, а затем *другой* объект разрушается.

## <a name="hstringoperator-operator"></a><a name="operator-equality"></a>HString:Оператор оператор

Указывает, являются ли эти два параметра равными.

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
Первый параметр для сравнения. *lHs* может `HString` быть `HStringReference` или объектом, или ручкой HSTRING.

*rhs*<br/>
Второй параметр для сравнения. *rhs* может `HString` быть `HStringReference` или объектом, или ручкой HSTRING.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параметры *lhs* и *rhs* равны; в противном случае, **ложные**.

## <a name="hstringoperator-operator"></a><a name="operator-inequality"></a>HString::Оператор!

Указывает, не являются ли эти два параметра равными.

```cpp
inline bool operator!=( const HString& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HStringReference& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HStringReference& rhs) throw()

inline bool operator!=( const HSTRING& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
Первый параметр для сравнения. *lHs* может `HString` быть `HStringReference` или объектом, или ручкой HSTRING.

*rhs*<br/>
Второй параметр для сравнения. *rhs* может `HString` быть `HStringReference` или объектом, или ручкой HSTRING.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параметры *lhs* и *rhs* не равны; в противном случае, **ложные**.

## <a name="hstringoperatorlt-operator"></a><a name="operator-less-than"></a>HString:Оператор&lt;

Указывает, является ли первый параметр меньше второго параметра.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>Параметры

*Lhs*<br/>
Первый параметр для сравнения. *lhs* может быть ссылкой на `HString`.

*rhs*<br/>
Второй параметр для сравнения. *rhs* может быть ссылкой на `HString`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если параметр *lhs* меньше параметра *rhs;* в противном случае, **ложные**.

## <a name="hstringrelease"></a><a name="release"></a>HString::Release

Удаляет базовое значение строки и инциализационирует текущий `HString` объект в пустое значение.

```cpp
void Release() throw()
```

## <a name="hstringset"></a><a name="set"></a>HString::Установить

Устанавливает значение текущего `HString` объекта к указанной строке или `HString` параметру широкого символа.

```cpp
HRESULT Set(
          const wchar_t* str) throw();
HRESULT Set(
          const wchar_t* str,
          unsigned int len
           ) throw();
HRESULT Set(
          const HSTRING& hstr
           ) throw();
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Строка расширенных символов.

*Лен*<br/>
Максимальная длина параметра *str,* назначенного `HString` текущему объекту.

*hstr*<br/>
Существующий объект `HString`.
