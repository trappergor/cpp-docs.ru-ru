---
title: Метод HString::MakeReference | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs:
- C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebc8632d273e650cf11e70177bbfbeb0e90e8601
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394859"
---
# <a name="hstringmakereference-method"></a>Метод HString::MakeReference

Создает `HStringReference` объект из указанного строкового параметра.

## <a name="syntax"></a>Синтаксис

```cpp
template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[ sizeDest]);

    template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[sizeDest],
              unsigned int len);
```

### <a name="parameters"></a>Параметры

*sizeDest*<br/>
Параметр шаблона, который указывает размер целевой `HStringReference` буфера.

*str*<br/>
Ссылка на строку расширенных символов.

*функция Len*<br/>
Максимальная длина *str* буфером параметров для использования в данной операции. Если *len* параметр не указан, весь *str* используется параметр.

## <a name="return-value"></a>Возвращаемое значение

`HStringReference` Объект, значение которого совпадает со значением указанного *str* параметра.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)