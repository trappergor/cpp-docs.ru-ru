---
title: Класс time_get_byname | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xloctime/std::time_get_byname
dev_langs:
- C++
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9858bfe4dc1d2451e4cd5054c5909aab27ef86c3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710012"
---
# <a name="timegetbyname-class"></a>Класс time_get_byname

Производный класс шаблона, описывающий объект, который можно использовать в качестве локального аспекта типа `time_get`\<CharType, InputIterator>.

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

*_Locname*<br/>
Именованный языковой стандарт.

*_Refs*<br/>
Начальное значение счетчика ссылок.

## <a name="requirements"></a>Требования

Его поведение определяется именованным языковым стандартом *_Locname*. Каждый конструктор инициализирует свой базовый объект с типом [time_get](../standard-library/time-get-class.md#time_get)\<CharType, InputIterator>( `_Refs`).

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
