---
title: Класс time_get_byname
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get_byname
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
ms.openlocfilehash: 040d140fa4250ad33e20d1c2724b6f563e865e6b
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742662"
---
# <a name="time_get_byname-class"></a>Класс time_get_byname

Шаблон производного класса описывает объект, который может выступать в качестве аспекта языкового стандарта типа `time_get` \<CharType, InputIterator> .

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class InputIterator =
    istreambuf_iterator<CharType, char_traits<CharType>>>
class time_get_byname : public time_get<CharType, InputIterator>
{
public:
    explicit time_get_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_get_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_get_byname()
};
```

### <a name="parameters"></a>Параметры

*_Locname*\
Именованный языковой стандарт.

*_Refs*\
Начальное значение счетчика ссылок.

## <a name="requirements"></a>Требования

Его поведение определяется с помощью именованного языкового стандарта *_Locname*. Каждый конструктор инициализирует свой базовый объект с помощью [time_get](../standard-library/time-get-class.md#time_get) \<CharType, InputIterator> ( `_Refs` ).

**Заголовок:**\<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
