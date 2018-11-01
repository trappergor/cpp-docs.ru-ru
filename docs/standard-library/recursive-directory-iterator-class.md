---
title: Класс recursive_directory_iterator
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: 52e6f738aa226dba26bae0cf6e97cd18d107d677
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593352"
---
# <a name="recursivedirectoryiterator-class"></a>Класс recursive_directory_iterator

Описывает итератор ввода, последовательный перебор имен файлов в каталоге, возможно по убыванию, рекурсивно просматривая подкаталоги. Для итератора `X`, выражение `*X` результатом которого является объект класса `directory_entry` , который создает оболочку, имя файла и все, что известно о его состоянии.

Дополнительные сведения и примеры кода см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Синтаксис

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Примечания

Шаблон класса хранит:

1. объект типа `stack<pair<directory_iterator, path>>`, который называется `mystack` здесь в целях надстройках, который представляет вложенные каталоги для

1. объект типа `directory_entry` вызывается `myentry` здесь, который представляет текущее имя файла в последовательности каталогов

1. объект типа **bool**, который называется `no_push` здесь, который записывает, отключен ли рекурсивный просмотр подкаталогов

1. объект типа `directory_options`, который называется `myoptions` здесь, который записывает параметры, установленные при создании.

Это созданный по умолчанию объект типа `recursive_directory_entry` итератором конец последовательности в `mystack.top().first` и представляет итератор конец последовательности. Например, если каталог `abc` с записями `def` (каталог), `def/ghi`, и `jkl`, код:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

вызывает метод visit с аргументами `path("abc/def/ghi")` и `path("abc/jkl")`. Вы можно определить перебор в поддереве каталога двумя способами:

1. Символьная ссылка каталога будет проверяться только в том случае, если при создании `recursive_directory_iterator` с `directory_options` аргумент, значение которого равно `directory_options::follow_directory_symlink`.

1. При вызове метода `disable_recursion_pending` следующего каталога, обнаруженного во время приращения не будут рекурсивно сканирования.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Создает документ `recursive_directory_iterator`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[Глубина](#depth)|Возвращает `mystack.size() - 1`, поэтому `pval` находится на нулевой глубине.|
|[disable_recursion_pending](#disable_recursion_pending)|Магазины **true** в `no_push`.|
|[Приращение](#increment)|Переходит к следующему файлу в последовательности.|
|[options](#options)|Возвращает `myoptions`.|
|[pop](#pop)|Возвращает следующий объект.|
|[recursion_pending](#recursion_pending)|Возвращает `!no_push`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](#op_neq)|Возвращает `!(*this == right)`.|
|[оператор=](#op_as)|Операторы-члены присваивания по умолчанию работают корректно.|
|[operator==](#op_eq)|Возвращает **true** только в том случае, если оба `*this` и *правой* являются итераторами конец последовательности или оба являются не end объекта последовательности итераторы.|
|[оператор*](#op_multiply)|Возвращает `myentry`.|
|[оператор>](#op_cast)|Возвращает `&**this`.|
|[оператор++](#op_increment)|С шагом `recursive_directory_iterator`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<filesystem >

**Пространство имен:** std::tr2::sys

## <a name="depth"></a> recursive_directory_iterator::Depth

Возвращает `mystack.size() - 1`, поэтому `pval` находится на нулевой глубине.

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a> recursive_directory_iterator::disable_recursion_pending

Магазины **true** в `no_push`.

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a> recursive_directory_iterator::Increment

Переходит к следующему файлу в последовательности.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>Параметры

*EC*<br/>
Указанный код ошибки.

### <a name="remarks"></a>Примечания

Функция пытается перейти к имени следующего файла во вложенной последовательности. Если в случае успешного выполнения она сохраняет имя этого файла в `myentry`; в противном случае она создает итератор конец последовательности.

## <a name="op_neq"></a> recursive_directory_iterator::operator! =

Возвращает `!(*this == right)`.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) для сравнения.

## <a name="op_as"></a> recursive_directory_iterator::operator =

Операторы-члены присваивания по умолчанию работают корректно.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*recursive_directory_iterator*<br/>
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) копируется в `recursive_directory_iterator`.

## <a name="op_eq"></a> recursive_directory_iterator::operator ==

Возвращает **true** только в том случае, если оба `*this` и *правой* являются итераторами конец последовательности или оба являются не end объекта последовательности итераторы.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Параметры

*right*<br/>
[Recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) для сравнения.

## <a name="op_multiply"></a> recursive_directory_iterator::operator *

Возвращает `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> recursive_directory_iterator::operator ->

Возвращает `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> recursive_directory_iterator::operator ++

С шагом `recursive_directory_iterator`.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Параметры

*int*<br/>
Заданное значение приращения.

### <a name="remarks"></a>Примечания

Первая функция-член вызывает `increment()`, затем возвращает `*this`. Вторая функция-член создает копию объекта, вызовы `increment()`, затем возвращает копию.

## <a name="options"></a> recursive_directory_iterator::Options

Возвращает `myoptions`.

```cpp
directory_options options() const;
```

## <a name="pop"></a> recursive_directory_iterator::POP

Возвращает следующий объект.

```cpp
void pop();
```

### <a name="remarks"></a>Примечания

Если `depth() == 0` объект становится итератор конец последовательности. В противном случае функция-член завершает проверку текущего (самого глубокого) каталога и возобновляет ее на следующем нижнем уровне глубины.

## <a name="recursion_pending"></a> recursive_directory_iterator::recursion_pending

Возвращает `!no_push`.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a> recursive_directory_iterator::recursive_directory_iterator

Создает документ `recursive_directory_iterator`.

```cpp
recursive_directory_iterator() noexcept;
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,
    error_code& ec) noexcept;
recursive_directory_iterator(const path& pval,
    directory_options opts);

recursive_directory_iterator(const path& pval,
    directory_options opts,
    error_code& ec) noexcept;
recursive_directory_iterator(const recursive_directory_iterator&) = default;
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Параметры

*PVal*<br/>
Заданный путь.

*error_code*<br/>
Указанный код ошибки.

*opts*<br/>
Параметры указанного каталога.

*recursive_directory_iterator*<br/>
`recursive_directory_iterator`, копией которого будет создаваемый `recursive_directory_iterator`.

### <a name="remarks"></a>Примечания

Первый конструктор создает итератор конца последовательности. Второй и третий конструкторы сохраняют **false** в `no_push` и `directory_options::none` в `myoptions`, затем пытаются открыть и прочитать *pval* как каталог. Если в случае успешного выполнения они инициализируют `mystack` и `myentry` для обозначения первое имя файла без directory во вложенной последовательности; в противном случае они создают итератор конец последовательности.

Четвертый и пятый конструкторы работают так же, как второй и третий, за исключением того, что сначала сохраняют *opts* в `myoptions`. Установленные по умолчанию конструкторы работают корректно.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)<br/>
