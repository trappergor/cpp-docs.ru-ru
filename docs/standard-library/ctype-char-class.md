---
title: Класс ctype&lt;char&gt;
ms.date: 11/04/2016
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
ms.openlocfilehash: 7fe1eef32741d63e7b2e2c2320d18f445784c44f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455457"
---
# <a name="ctypeltchargt-class"></a>Класс ctype&lt;char&gt;

Класс является явной специализацией класса `ctype\<CharType>` шаблона для типа **char**, описывающий объект, который может служить в качестве аспекта языкового стандарта для описания различных свойств символа типа **char**.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
class ctype<char>
: public ctype_base
{
public:
    typedef char _Elem;
    typedef _Elem char_type;
    bool is(
    mask _Maskval,
    _Elem _Ch) const;

    const _Elem* is(
    const _Elem* first,
    const _Elem* last,
    mask* dest) const;

    const _Elem* scan_is(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;

    const _Elem* scan_not(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;

    _Elem tolower(
    _Elem _Ch) const;

    const _Elem* tolower(
    _Elem* first,
    const _Elem* last) const;

    _Elem toupper(
    _Elem _Ch) const;

    const _Elem* toupper(
    _Elem* first,
    const _Elem* last) const;

    _Elem widen(
    char _Byte) const;

    const _Elem* widen(
    const char* first,
    const char* last,
    _Elem* dest) const;

    const _Elem* _Widen_s(
    const char* first,
    const char* last,
    _Elem* dest,
    size_t dest_size) const;

    _Elem narrow(
    _Elem _Ch,
    char _Dflt = '\0') const;

    const _Elem* narrow(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest) const;

    const _Elem* _Narrow_s(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest,
    size_t dest_size) const;

    static locale::id& id;
    explicit ctype(
    const mask* _Table = 0,
    bool _Deletetable = false,
    size_t _Refs = 0);

protected:
    virtual ~ctype();
//other protected members
};
```

## <a name="remarks"></a>Примечания

Явная специализация отличается от класса шаблона несколькими аспектами.

- Объект класса ctype < `char`> сохраняет указатель на первый элемент таблицы маски ctype, массив элементов UCHAR_MAX + 1 типа. `ctype_base::mask` Он также хранит объект логического типа, указывающий, следует ли удалять массив (с помощью `operator delete[]`), когда удаляется объект ctype\< **Elem**>.

- Его единственный открытый конструктор позволяет указать `tab`, таблицу маски ctype и `del`логический объект, который имеет значение true, если массив должен быть удален при уничтожении объекта CType < `char`>, а также счетчика ссылок. параметр ReFS.

- Защищенная функция `table` Member возвращает хранимую таблицу маски ctype.

- Объект `table_size` статического элемента указывает минимальное число элементов в таблице маски ctype.

- Защищенная статическая функция `classic_table`-член (Возвращает таблицу маски ctype, соответствующую языковому стандарту "C".

- Отсутствуют защищенные виртуальные функции-члены [do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is) или [do_scan_not](../standard-library/ctype-class.md#do_scan_not). Соответствующие открытые функции-члены самостоятельно выполняют эквивалентные операции.

Функции-члены [do_narrow](../standard-library/ctype-class.md#do_narrow) и [do_widen](../standard-library/ctype-class.md#do_widen) копируют элементы без изменений.

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Класс facet](locale-class.md#facet_class)\
[Класс ctype_base](../standard-library/ctype-base-class.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
