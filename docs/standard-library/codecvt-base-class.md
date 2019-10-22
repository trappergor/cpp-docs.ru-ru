---
title: Класс codecvt_base
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: 6fca9b2130407b165a7a7bfb1fb2a9ec81774e20
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689892"
---
# <a name="codecvt_base-class"></a>Класс codecvt_base

Базовый класс для класса codecvt, который используется для определения типа перечисления, называемого `result`, используемого в качестве возвращаемого типа для функций-членов аспекта для указания результата преобразования.

## <a name="syntax"></a>Синтаксис

```cpp
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```

## <a name="remarks"></a>Заметки

Класс описывает перечисление, общее для всех специализаций шаблона класса [codecvt](../standard-library/codecvt-class.md). Результат перечисления описывает возможные возвращаемые значения из [do_in](../standard-library/codecvt-class.md#do_in) или [do_out](../standard-library/codecvt-class.md#do_out):

- `ok`, если преобразование между внутренними и внешними кодировками символов выполнено.

- `partial`, если назначение недостаточно велико для успешности преобразования.

- `error`, если исходная последовательность сформирована неправильно.

- `noconv`, если функция не выполняет преобразование;

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
