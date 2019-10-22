---
title: Класс messages_byname
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_byname
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
ms.openlocfilehash: 56d8931cb404d9c0f3f5113f8b2ca0f1158209f2
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689334"
---
# <a name="messages_byname-class"></a>Класс messages_byname

Шаблон производного класса описывает объект, который можно использовать в качестве аспекта сообщения для данного языкового стандарта, что позволяет получать локализованные сообщения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```

### <a name="parameters"></a>Параметры

*_Locname* \
Именованный языковой стандарт.

*_Refs* \
Начальное значение счетчика ссылок.

## <a name="remarks"></a>Заметки

Его поведение определяется с помощью именованного языкового стандарта *_Locname*. Каждый конструктор инициализирует свой базовый объект с [сообщениями](../standard-library/messages-class.md#messages)\<CharType>( `_Refs`).

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
