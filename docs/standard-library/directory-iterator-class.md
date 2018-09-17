---
title: Класс directory_iterator | Документы Майкрософт
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
dev_langs:
- C++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.workload:
- cplusplus
ms.openlocfilehash: dd5fedb8869533755546089bdee903403f30dcea
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726379"
---
# <a name="directoryiterator-class"></a>Класс directory_iterator

Описывает итератор ввода, выполняющий последовательный перебор имен файлов в каталоге. Для итератора `X`, выражение `*X` результатом которого является объект класса `directory_entry` , который создает оболочку, имя файла и все, что известно о его состоянии.

Класс сохраняет объект типа `path`, который называется `mydir` здесь для целей надстройках, которая представляет имя каталога для упорядочивания, и объект типа `directory_entry` вызывается `myentry` здесь, который представляет текущий Имя файла в последовательности каталогов. Это созданный по умолчанию объект типа `directory_entry` имеет пустой `mydir` pathname и представляет итератор конец последовательности.

Например, если каталог `abc` с записями `def` и `ghi`, код:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

вызовет `visit` с аргументами `path("abc/def")` и `path("abc/ghi")`.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class directory_iterator;
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[directory_iterator](#directory_iterator)|Создает итератор ввода, выполняющий последовательный перебор имен файлов в каталоге.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[Приращение](#increment)|Пытается перейти к следующему файлу в каталоге.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор!=](#op_neq)|Возвращает `!(*this == right)`.|
|[оператор=](#op_as)|Операторы-члены присваивания по умолчанию работают корректно.|
|[оператор==](#op_eq)|Возвращает **true** только в том случае, если оба `*this` и *правой* являются итераторами конец последовательности или оба являются не end объекта последовательности итераторы.|
|[оператор*](#op_star)|Возвращает `myentry`.|
|[оператор>](#op_cast)|Возвращает `&**this`.|
|[оператор++](#op_increment)|Вызовы `increment()`, затем возвращает `*this`, или создает копию объекта, вызовы `increment()`, затем возвращает копию.|

## <a name="requirements"></a>Требования

**Заголовок:** \<experimental/filesystem>

**Пространство имен:** std::experimental::filesystem

## <a name="directory_iterator"></a> directory_iterator::directory_iterator

Первый конструктор создает итератор конца последовательности. Второй и третий конструкторы сохраняют *pval* в `mydir`, затем пытаются открыть и прочитать `mydir` как каталог. Если в случае успешного выполнения они хранят первое имя файла в каталоге в `myentry`; противном случае — создают итератор конец последовательности.

Установленные по умолчанию конструкторы работают корректно.

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*PVal*<br/>
Путь имя сохраненного файла.

*EC*<br/>
Код состояния ошибки.

*directory_iterator*<br/>
Сохраненный объект.

## <a name="increment"></a> directory_iterator::Increment

Функция пытается перейти к следующему файлу в каталоге. Если в случае успешного выполнения она сохраняет имя этого файла в `myentry`; в противном случае она создает итератор конец последовательности.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="op_neq"></a> directory_iterator::operator! =

Оператор-член возвращает `!(*this == right)`.

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_iterator](../standard-library/directory-iterator-class.md) , с которым производится сравнение `directory_iterator`.

## <a name="op_as"></a> directory_iterator::operator =

Операторы-члены присваивания по умолчанию работают корректно.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_iterator](../standard-library/directory-iterator-class.md) копируется в `directory_iterator`.

## <a name="op_eq"></a> directory_iterator::operator ==

Оператор-член возвращает **true** только в том случае, если оба `*this` и *правой* являются итераторами конец последовательности или оба являются не end объекта последовательности итераторы.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Directory_iterator](../standard-library/directory-iterator-class.md) , с которым производится сравнение `directory_iterator`.

## <a name="op_star"></a> directory_iterator::operator *

Оператор-член возвращает `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> directory_iterator::operator ->

Функция-член возвращает значение `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> directory_iterator::operator ++

Первая функция-член вызывает `increment()`, затем возвращает `*this`. Вторая функция-член создает копию объекта, вызовы `increment()`, затем возвращает копию.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>Параметры

*int*<br/>
Количество шагов приращения.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)<br/>
