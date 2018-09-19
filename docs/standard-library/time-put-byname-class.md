---
title: Класс time_put_byname | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xloctime/std::time_put_byname
dev_langs:
- C++
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62d78fb7c2b9cbaee62baf59636303f90177cf7b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699599"
---
# <a name="timeputbyname-class"></a>Класс time_put_byname

Производный класс шаблона, описывающий объект, который можно использовать в качестве локального аспекта типа `time_put`\< CharType, OutputIterator >.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```

### <a name="parameters"></a>Параметры

*_Locname*<br/>
Имя языкового стандарта.

*_Refs*<br/>
Начальное значение счетчика ссылок.

## <a name="remarks"></a>Примечания

Его поведение определяется [с именем](../standard-library/locale-class.md#name) языкового стандарта *_Locname*. Каждый конструктор инициализирует свой базовый объект с [time_put](../standard-library/time-put-class.md#time_put)\<CharType, Inputiterator > (`_Refs`).

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
