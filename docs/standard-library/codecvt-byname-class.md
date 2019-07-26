---
title: Класс codecvt_byname
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_byname
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
ms.openlocfilehash: 62781d575d6b9dda3f3c1e2a744091221c6f9584
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459853"
---
# <a name="codecvtbyname-class"></a>Класс codecvt_byname

Производный класс шаблона, описывающий объект, который можно использовать как аспект сортировки данного языкового стандарта, предоставляющий возможность извлечения данных касательно преобразований по соответствующему культурному региону.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, class Byte, class StateType>
class codecvt_byname: public codecvt<CharType, Byte, StateType> {
public:
    explicit codecvt_byname(
    const char* _Locname,
    size_t _Refs = 0);
```

```cpp
explicit codecvt_byname(
    const string& _Locname,
    size_t _Refs = 0);
```

```cpp
protected:
    virtual ~codecvt_byname();

};
```

### <a name="parameters"></a>Параметры

*_Locname*\
Именованный языковой стандарт.

*_Refs*\
Начальное значение счетчика ссылок.

## <a name="remarks"></a>Примечания

Аспекты Byname создаются автоматически при создании именованного языкового стандарта.

Его поведение определяется с помощью именованного языкового стандарта *_Locname*. Каждый конструктор инициализирует свой базовый объект с [codecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`).

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
