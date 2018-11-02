---
title: Класс codecvt_base
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: 6f957c39f9c78fd182b7ba2a14bdab7f27db56ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520631"
---
# <a name="codecvtbase-class"></a>Класс codecvt_base

Базовый класс для класса codecvt, используемый для определения типа перечисления называются `result`, которое используется в качестве возвращаемого типа для функций-членов аспекта, чтобы показать результат преобразования.

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

## <a name="remarks"></a>Примечания

Данный класс описывает перечисление, общее для всех специализаций класса-шаблона [codecvt](../standard-library/codecvt-class.md). Результат перечисления описывает возможные возвращаемые значения из [do_in](../standard-library/codecvt-class.md#do_in) или [do_out](../standard-library/codecvt-class.md#do_out):

- `ok` Если преобразование между внутренней и внешней кодировками символов выполняется успешно.

- `partial` Если в месте назначения недостаточно велик для успешного преобразования.

- `error` Если исходная последовательность имеет формат.

- `noconv`, если функция не выполняет преобразование;

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
