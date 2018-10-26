---
title: Класс HString | Документация Майкрософт
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
- corewrappers/Microsoft::WRL::Wrappers::HString::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
- corewrappers/Microsoft::WRL::Wrappers::HString::Get
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8165a404924b997d70d0097c28ac7d34ade92fc3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063865"
---
# <a name="hstring-class"></a>Класс HString

Вспомогательный класс для управления жизненным циклом [HSTRING](/windows/desktop/WinRT/hstring) с помощью шаблон RAII.

## <a name="syntax"></a>Синтаксис

```cpp
class HString;
```

## <a name="remarks"></a>Примечания

Среда выполнения Windows предоставляет доступ к строкам посредством [HSTRING](/windows/desktop/WinRT/hstring) дескрипторов. `HString` Класс предоставляет удобные функции и операторы для упрощения использования дескрипторов HSTRING. Этот класс может обрабатывать время существования HSTRING, которому он принадлежит через шаблон RAII.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                | Описание
----------------------------------- | -----------------------------------------------------
[HString::HString](#hstring)        | Инициализирует новый экземпляр класса `HString`.
[HString:: ~ HString](#tilde-hstring) | Удаляет текущий экземпляр `HString` класса.

### <a name="public-methods"></a>Открытые методы

Имя                                     | Описание
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString::Attach](#attach)               | Связывает указанный `HString` объект с текущим `HString` объекта.
[HString::CopyTo](#copyto)               | Копирует текущий `HString` объект в объект HSTRING.
[HString::Detach](#detach)               | Отменяет связывание заданных `HString` объект с его базовым значением.
[HString::Get](#get)                     | Получает значение базового дескриптора HSTRING.
[HString::GetAddressOf](#getaddressof)   | Извлекает указатель на базовый дескриптор HSTRING.
[HString::IsValid](#isvalid)             | Указывает, является ли текущий `HString` объект является допустимым.
[HString::MakeReference](#makereference) | Создает `HStringReference` объект из указанного строкового параметра.
[HString::Release](#release)             | Удаляет базовое строковое значение и инициализирует текущий `HString` объекта пустое значение.
[HString::Set](#set)                     | Задает значение текущего `HString` объекта с помощью указанной строки расширенных символов или `HString` параметра.

### <a name="public-operators"></a>Открытые операторы

Имя                                         | Описание
-------------------------------------------- | ----------------------------------------------------------------------------
[Оператор HString::operator =](#operator-assign)       | Перемещает значение другого `HString` объект с текущим `HString` объекта.
[Оператор HString::operator ==](#operator-equality)    | Указывает, равны ли два параметра.
[Оператор HString::operator! =](#operator-inequality)  | Указывает, действительно ли два параметра не равны.
[Оператор HString::operator&lt;](#operator-less-than) | Указывает, является ли первый параметр меньше значения второго параметра.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HString`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="tilde-hstring"></a>HString:: ~ HString

Удаляет текущий экземпляр `HString` класса.

```cpp
~HString() throw()
```

## <a name="attach"></a>HString::Attach

Связывает указанный `HString` объект с текущим `HString` объекта.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>Параметры

*HSTR*<br/>
Существующий объект `HString`.

## <a name="copyto"></a>HString::CopyTo

Копирует текущий `HString` объект в объект HSTRING.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Параметры

*str*<br/>
HSTRING, который получает копию.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [WindowsDuplicateString](https://msdn.microsoft.com/library/br224634.aspx) функции.

## <a name="detach"></a>HString::Detach

Отменяет связывание заданных `HString` объект с его базовым значением.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Возвращаемое значение

Базовый `HString` значение до запуска операции отсоединения.

## <a name="get"></a>HString::Get

Получает значение базового дескриптора HSTRING.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Возвращаемое значение

Значение базового дескриптора HSTRING.

## <a name="getaddressof"></a>HString::GetAddressOf

Извлекает указатель на базовый дескриптор HSTRING.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовый дескриптор HSTRING.

### <a name="remarks"></a>Примечания

После этой операции строковое значение базового дескриптора HSTRING будет уничтожено.

## <a name="hstring"></a>HString::HString

Инициализирует новый экземпляр класса `HString`.

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>Параметры

*HSTR*<br/>
Дескриптор HSTRING.

*other*<br/>
Существующий объект `HString`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует новый `HString` объект, который является пустым.

Второй конструктор инициализирует новый `HString` значение существующего *других* параметра, а затем удаляет *других* параметра.

## <a name="isvalid"></a>HString::IsValid

Указывает, является ли текущий `HString` объект пуст или не.

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>Параметры

**значение true,** Если текущий `HString` объект не является пустой; в противном случае **false**.

## <a name="makereference"></a>HString::MakeReference

Создает `HStringReference` объект из указанного строкового параметра.

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

*sizeDest*<br/>
Параметр шаблона, который указывает размер целевой `HStringReference` буфера.

*str*<br/>
Ссылка на строку расширенных символов.

*функция Len*<br/>
Максимальная длина *str* буфером параметров для использования в данной операции. Если *len* параметр не указан, весь *str* используется параметр.

### <a name="return-value"></a>Возвращаемое значение

`HStringReference` Объект, значение которого совпадает со значением указанного *str* параметра.

## <a name="operator-assign"></a>Оператор HString::operator =-оператор

Перемещает значение другого `HString` объект с текущим `HString` объекта.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>Параметры

*other*<br/>
Существующий объект `HString`.

### <a name="remarks"></a>Примечания

Значение существующего *других* объект копируется в текущий `HString` объекта, а затем *других* уничтожении объекта.

## <a name="operator-equality"></a>Оператор HString::operator ==-оператор

Указывает, равны ли два параметра.

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

*lhs*<br/>
Первый параметр для сравнения. *LHS* может быть `HString` или `HStringReference` объекта или дескриптором HSTRING.

*правая часть*<br/>
Второй параметр для сравнения. *rhs* может быть `HString` или `HStringReference` объекта или дескриптором HSTRING.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* и *rhs* параметры равны; в противном случае — значение **false**.

## <a name="operator-inequality"></a>Оператор HString::operator! =-оператор

Указывает, действительно ли два параметра не равны.

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

*lhs*<br/>
Первый параметр для сравнения. *LHS* может быть `HString` или `HStringReference` объекта или дескриптором HSTRING.

*правая часть*<br/>
Второй параметр для сравнения. *rhs* может быть `HString` или `HStringReference` объекта или дескриптором HSTRING.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* и *rhs* параметры не равны; в противном случае — значение **false**.

## <a name="operator-less-than"></a>Оператор HString::operator&lt; оператор

Указывает, является ли первый параметр меньше значения второго параметра.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый параметр для сравнения. *LHS* можно ссылаться на `HString`.

*правая часть*<br/>
Второй параметр для сравнения. *правая часть* можно ссылаться на `HString`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* параметр меньше, чем *rhs* параметра; в противном случае **false**.

## <a name="release"></a>HString::Release

Удаляет базовое строковое значение и инициализирует текущий `HString` объекта пустое значение.

```cpp
void Release() throw()
```

## <a name="set"></a>HString::Set

Задает значение текущего `HString` объекта с помощью указанной строки расширенных символов или `HString` параметра.

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

*str*<br/>
Строка расширенных символов.

*функция Len*<br/>
Максимальная длина *str* параметр, который будет назначен текущий `HString` объекта.

*HSTR*<br/>
Существующий объект `HString`.
