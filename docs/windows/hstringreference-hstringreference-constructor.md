---
title: Конструктор HStringReference::HStringReference | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs:
- C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6123f87abb9922a9736ac56f64d28e78887a0fdd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403587"
---
# <a name="hstringreferencehstringreference-constructor"></a>Конструктор HStringReference::HStringReference

Инициализирует новый экземпляр класса **HStringReference** класса.

## <a name="syntax"></a>Синтаксис

```cpp
template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest]) throw();

template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest],
                 unsigned int len) throw();

HStringReference(HStringReference&& other) throw();
```

### <a name="parameters"></a>Параметры

*sizeDest*<br/>
Параметр шаблона, который указывает размер целевой **HStringReference** буфера.

*str*<br/>
Ссылка на строку расширенных символов.

*функция Len*<br/>
Максимальная длина *str* буфером параметров для использования в данной операции. Если *len* параметр не указан, весь *str* используется параметр. Если *len* больше, чем *sizeDest*, *len* присваивается *sizeDest*-1.

*other*<br/>
Другой **HStringReference** объекта.

## <a name="remarks"></a>Примечания

Первый конструктор инициализирует новый **HStringReference** объект того же размера, как параметр *str*.

Второй конструктор инициализирует новый **HStringReference** объект, размер которого определен параметром *len*.

Третий конструктор инициализирует новый **HStringReference** объекта к значению *других* параметра, а затем удаляет *других* параметра.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HStringReference](../windows/hstringreference-class.md)