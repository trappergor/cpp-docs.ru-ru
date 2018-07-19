---
title: Класс codecvt_base | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a471cdd63ed46e15c9ec41968ed341eefaf36963
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965396"
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
