---
title: Класс moneypunct_byname
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct_byname
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
ms.openlocfilehash: 003ba2136e779c444c7edad9b1759a861a8b0803
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574441"
---
# <a name="moneypunctbyname-class"></a>Класс moneypunct_byname

Производный класс шаблона, описывающий объект, который можно использовать в качестве аспекта `moneypunct` для заданного языкового стандарта, для возможности форматирования полей ввода или вывода денежной суммы.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, bool Intl = false>
class moneypunct_byname : public moneypunct<CharType, Intl>
{
public:
    explicit moneypunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit moneypunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~moneypunct_byname();

};
```

## <a name="remarks"></a>Примечания

Его поведение определяется именованным языковым стандартом `_Locname`. Каждый конструктор инициализирует свой базовый объект с [moneypunct](../standard-library/moneypunct-class.md#moneypunct)\<CharType, Intl>( `_Refs`).

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
