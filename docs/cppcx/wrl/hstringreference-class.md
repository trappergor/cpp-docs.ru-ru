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
ms.openlocfilehash: 591af0d66c9c209ba56310a0bd5cf5cd74e34929
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498348"
---
# <a name="hstringreference-class"></a>Класс HStringReference

Представляет HSTRING, созданный из существующей строки.

## <a name="syntax"></a>Синтаксис

```cpp
class HStringReference;
```

## <a name="remarks"></a>Примечания

Время существования резервного буфера в новом HSTRING не управляется среда выполнения Windows. Вызывающий объект выделяет исходную строку в кадре стека, чтобы избежать выделения кучи и избежать риска утечки памяти. Кроме того, вызывающий объект должен гарантировать, что исходная строка остается неизменной в течение времени существования присоединенного HSTRING. Дополнительные сведения см. в разделе [функция виндовскреатестрингреференце](/windows/win32/api/winstring/nf-winstring-windowscreatestringreference).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

name                                                    | Описание
------------------------------------------------------- | -----------------------------------------------------------
[HStringReference:: HStringReference](#hstringreference) | Инициализирует новый экземпляр класса `HStringReference`.

### <a name="public-methods"></a>Открытые методы

Член                              | Описание
----------------------------------- | ------------------------------------------------------------------
[HStringReference:: CopyTo](#copyto) | Копирует текущий `HStringReference` объект в объект HString.
[HStringReference:: Get](#get)       | Получает значение базового маркера HSTRING.
[HStringReference:: Жетравбуффер](#getrawbuffer) | Извлекает указатель на базовые строковые данные.

### <a name="public-operators"></a>Открытые операторы

name                                                  | Описание
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[HStringReference:: operator =](#operator-assign)       | Перемещает значение другого `HStringReference` объекта в текущий `HStringReference` объект.
[HStringReference:: operator = =](#operator-equality)    | Указывает, равны ли два параметра.
[HStringReference:: operator! =](#operator-inequality)  | Указывает, являются ли два параметра неравными.
[HStringReference:: operator&lt;](#operator-less-than) | Указывает, меньше ли первый параметр второго параметра.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HStringReference`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс. h

**Пространство имен:** Программы Microsoft:: WRL:: оболочки

## <a name="copyto"></a>HStringReference:: CopyTo

Копирует текущий `HStringReference` объект в объект HString.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Параметры

*str*<br/>
HSTRING, который получает копию.

### <a name="remarks"></a>Примечания

Этот метод вызывает функцию [виндовсдупликатестринг](/windows/win32/api/winstring/nf-winstring-windowsduplicatestring) .

## <a name="get"></a>HStringReference:: Get

Получает значение базового маркера HSTRING.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Возвращаемое значение

Значение базового дескриптора HSTRING.

## <a name="getrawbuffer"></a>HStringReference:: Жетравбуффер

Извлекает указатель на базовые строковые данные.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```
### <a name="parameters"></a>Параметры

*Длина* Указатель на переменную **int** , которая получает длину данных.

### <a name="return-value"></a>Возвращаемое значение

**Константный** указатель на базовые строковые данные.

## <a name="hstringreference"></a>HStringReference:: HStringReference

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

*самый заданный размер*<br/>
Параметр шаблона, указывающий размер буфера назначения `HStringReference` .

*str*<br/>
Ссылка на строку расширенных символов.

*len*<br/>
Максимальная длина буфера параметров *str* для использования в этой операции. Если параметр *Len* не указан, используется весь параметр *str* . Если *Len* больше, чем *size*, то параметр *Len* имеет значение *size*-1.

*other*<br/>
Другой `HStringReference` объект.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует новый `HStringReference` объект того же размера, что и *str*параметра.

Второй конструктор инициализирует новый `HStringReference` объект, размер которого спеЦифеид параметром *Len*.

Третий конструктор инициализирует новый `HStringReference` объект значением *другого* параметра, а затем уничтожает *другой* параметр.

## <a name="operator-assign"></a>HStringReference:: operator =

Перемещает значение другого `HStringReference` объекта в текущий `HStringReference` объект.

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>Параметры

*other*<br/>
Существующий объект `HStringReference`.

### <a name="remarks"></a>Примечания

Значение существующего объекта копируется в текущий `HStringReference` объект, а затем удаляется *другой* объект.

## <a name="operator-equality"></a>HStringReference:: operator = =

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

*LHS*<br/>
Первый сравниваемый параметр. *LHS* может быть `HStringReference` объектом или обработчиком HString.

*rhs*<br/>
Второй сравниваемый параметр.  *RHS* может быть `HStringReference` объектом или обработчиком HString.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если параметры *LHS* и *RHS* равны; в противном случае — **значение false**.

## <a name="operator-inequality"></a>HStringReference:: operator! =

Указывает, являются ли два параметра неравными.

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

*LHS*<br/>
Первый сравниваемый параметр. *LHS* может быть `HStringReference` объектом или обработчиком HString.

*rhs*<br/>
Второй сравниваемый параметр.  *RHS* может быть `HStringReference` объектом или обработчиком HString.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если параметры *LHS* и *RHS* не равны; в противном случае — **значение false**.

## <a name="operator-less-than"></a>HStringReference:: operator&lt;

Указывает, меньше ли первый параметр второго параметра.

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
Первый сравниваемый параметр. *LHS* может быть ссылкой на `HStringReference`.

*rhs*<br/>
Второй сравниваемый параметр.  *RHS* может быть ссылкой на `HStringReference`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если параметр *LHS* меньше параметра *RHS* ; в противном случае — **значение false**.
