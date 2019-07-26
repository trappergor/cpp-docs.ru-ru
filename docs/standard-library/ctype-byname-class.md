---
title: Класс ctype_byname
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: 0b0f33781cc9f1f54661a44a5434c94316432a45
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457895"
---
# <a name="ctypebyname-class"></a>Класс ctype_byname

Производный класс шаблона, описывающий объект, который можно использовать в качестве аспекта ctype заданного языкового стандарта, позволяющий классифицировать символы и выполнять преобразование символов в другой регистр, а также из внутреннего набора символов в набор символов, заданный для языкового стандарта, и наоборот.

## <a name="syntax"></a>Синтаксис

```cpp
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```

## <a name="remarks"></a>Примечания

Его поведение определяется именованным языковым стандартом `_Locname`. Каждый конструктор инициализирует свой базовый объект с [ctype](../standard-library/ctype-class.md)\<CharType>( `_Refs`) или эквивалент для базового класса `ctype<char>`.

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
