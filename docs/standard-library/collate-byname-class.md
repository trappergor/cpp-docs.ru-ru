---
title: Класс collate_byname
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate_byname
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
ms.openlocfilehash: 46eb139bafcf7368688f32cce37e38362c158c91
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405187"
---
# <a name="collatebyname-class"></a>Класс collate_byname

Производный класс шаблона, описывающий объект, который можно использовать как аспект сортировки данного языкового стандарта, предоставляющий возможность извлечения данных касательно сортировки строк по соответствующему культурному региону.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```

### <a name="parameters"></a>Параметры

*_Locname*<br/>
Именованный языковой стандарт.

*_Refs*<br/>
Начальное значение счетчика ссылок.

## <a name="remarks"></a>Примечания

Класс шаблона, описывающий объект, который может служить в качестве [аспекта языкового стандарта](../standard-library/locale-class.md#facet_class) типа [collate](../standard-library/collate-class.md#collate)\<CharType>. Его поведение определяется [с именем](../standard-library/locale-class.md#name) языкового стандарта *_Locname*. Каждый конструктор инициализирует свой базовый объект с [collate](../standard-library/collate-class.md#collate)\<CharType>( `_Refs`).

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
