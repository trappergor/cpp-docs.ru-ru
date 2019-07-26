---
title: Класс messages_byname
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_byname
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
ms.openlocfilehash: b8fe1ab2db792819831f5c50aa99a02559f71cdd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451809"
---
# <a name="messagesbyname-class"></a>Класс messages_byname

Производный класс шаблона описывает объект, который можно использовать в качестве аспекта сообщения для заданного языкового стандарта, что позволяет извлекать локализованные сообщения.

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

*_Locname*\
Именованный языковой стандарт.

*_Refs*\
Начальное значение счетчика ссылок.

## <a name="remarks"></a>Примечания

Его поведение определяется с помощью именованного языкового стандарта *_Locname*. Каждый конструктор инициализирует свой базовый объект с [сообщениями](../standard-library/messages-class.md#messages)\<CharType>( `_Refs`).

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
