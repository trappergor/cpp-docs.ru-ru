---
title: Класс HStringReference
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::Get
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
ms.openlocfilehash: b9d2e49d0a7e1321e2259c06e1313a90d55dc90e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785189"
---
# <a name="hstringreference-class"></a>Класс HStringReference

Представляет HSTRING, созданный из существующей строки.

## <a name="syntax"></a>Синтаксис

```cpp
class HStringReference;
```

## <a name="remarks"></a>Примечания

Время существования буфера резервного копирования в новом HSTRING не управляется средой выполнения Windows. Вызывающий объект выделяет строку источника в кадре стека во избежание выделения памяти для кучи и для исключения риска утечки памяти. Кроме того вызывающий объект должен убедиться, что строка источника остается неизменной в течение времени существования подключенного HSTRING. Дополнительные сведения см. в разделе [WindowsCreateStringReference функция](/windows/desktop/api/winstring/nf-winstring-windowscreatestringreference).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

name                                                    | Описание
------------------------------------------------------- | -----------------------------------------------------------
[HStringReference::HStringReference](#hstringreference) | Инициализирует новый экземпляр класса `HStringReference`.

### <a name="public-methods"></a>Открытые методы

Член                              | Описание
----------------------------------- | ------------------------------------------------------------------
[HStringReference::CopyTo](#copyto) | Копирует текущий `HStringReference` объект в объект HSTRING.
[HStringReference::Get](#get)       | Получает значение базового дескриптора HSTRING.

### <a name="public-operators"></a>Открытые операторы

name                                                  | Описание
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[Оператор HStringReference::operator =](#operator-assign)       | Перемещает значение другого `HStringReference` объект с текущим `HStringReference` объекта.
[Оператор HStringReference::operator ==](#operator-equality)    | Указывает, равны ли два параметра.
[Оператор HStringReference::operator! =](#operator-inequality)  | Указывает, действительно ли два параметра не равны.
[Оператор HStringReference::operator&lt;](#operator-less-than) | Указывает, является ли первый параметр меньше значения второго параметра.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HStringReference`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers

## <a name="copyto"></a>HStringReference::CopyTo

Копирует текущий `HStringReference` объект в объект HSTRING.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Параметры

*str*<br/>
HSTRING, который получает копию.

### <a name="remarks"></a>Примечания

Этот метод вызывает метод [WindowsDuplicateString](/windows/desktop/api/winstring/nf-winstring-windowsduplicatestring) функции.

## <a name="get"></a>HStringReference::Get

Получает значение базового дескриптора HSTRING.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Возвращаемое значение

Значение базового дескриптора HSTRING.

## <a name="hstringreference"></a>HStringReference::HStringReference

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

*sizeDest*<br/>
Параметр шаблона, который указывает размер целевой `HStringReference` буфера.

*str*<br/>
Ссылка на строку расширенных символов.

*функция Len*<br/>
Максимальная длина *str* буфером параметров для использования в данной операции. Если *len* параметр не указан, весь *str* используется параметр. Если *len* больше, чем *sizeDest*, *len* присваивается *sizeDest*-1.

*other*<br/>
Другой `HStringReference` объекта.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует новый `HStringReference` объект того же размера, как параметр *str*.

Второй конструктор инициализирует новый `HStringReference` объект, размер которого определен параметром *len*.

Третий конструктор инициализирует новый `HStringReference` объекта к значению *других* параметра, а затем удаляет *других* параметра.

## <a name="operator-assign"></a>Оператор HStringReference::operator =

Перемещает значение другого `HStringReference` объект с текущим `HStringReference` объекта.

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>Параметры

*other*<br/>
Существующий объект `HStringReference`.

### <a name="remarks"></a>Примечания

Значение существующего *других* объект копируется в текущий `HStringReference` объекта, а затем *других* уничтожении объекта.

## <a name="operator-equality"></a>Оператор HStringReference::operator ==

Указывает, равны ли два параметра.

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

*lhs*<br/>
Первый параметр для сравнения. *LHS* может быть `HStringReference` объекта или дескриптором HSTRING.

*правая часть*<br/>
Второй параметр для сравнения.  *правая часть* может быть `HStringReference` объекта или дескриптором HSTRING.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* и *rhs* параметры равны; в противном случае — значение **false**.

## <a name="operator-inequality"></a>Оператор HStringReference::operator! =

Указывает, действительно ли два параметра не равны.

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

*lhs*<br/>
Первый параметр для сравнения. *LHS* может быть `HStringReference` объекта или дескриптором HSTRING.

*правая часть*<br/>
Второй параметр для сравнения.  *правая часть* может быть `HStringReference` объекта или дескриптором HSTRING.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* и *rhs* параметры не равны; в противном случае — значение **false**.

## <a name="operator-less-than"></a>Оператор HStringReference::operator&lt;

Указывает, является ли первый параметр меньше значения второго параметра.

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>Параметры

*lhs*<br/>
Первый параметр для сравнения. *LHS* можно ссылаться на `HStringReference`.

*правая часть*<br/>
Второй параметр для сравнения.  *правая часть* можно ссылаться на `HStringReference`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если *lhs* параметр меньше, чем *rhs* параметра; в противном случае **false**.
