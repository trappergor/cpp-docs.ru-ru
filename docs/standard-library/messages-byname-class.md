---
title: Класс messages_byname | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmes/std::messages_byname
dev_langs:
- C++
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e03cb627e7e9db40d56a69112977d87141626696
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100448"
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

*_Locname*<br/>
Именованный языковой стандарт.

*_Refs*<br/>
Начальное значение счетчика ссылок.

## <a name="remarks"></a>Примечания

Его поведение определяется именованным языковым стандартом *_Locname*. Каждый конструктор инициализирует свой базовый объект с [сообщениями](../standard-library/messages-class.md#messages)\<CharType>( `_Refs`).

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
