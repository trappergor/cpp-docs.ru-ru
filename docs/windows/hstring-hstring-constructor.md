---
title: Конструктор HString::HString | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59ec7c1635b825cc300e28e5c02e2a3864a6c123
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442257"
---
# <a name="hstringhstring-constructor"></a>Конструктор HString::HString

Инициализирует новый экземпляр класса **HString** класса.

## <a name="syntax"></a>Синтаксис

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

#### <a name="parameters"></a>Параметры

*HSTR*<br/>
Дескриптор HSTRING.

*other*<br/>
Существующий **HString** объекта.

## <a name="remarks"></a>Примечания

Первый конструктор инициализирует новый **HString** объект, который является пустым.

Второй конструктор инициализирует новый **HString** значение существующего *других* параметра, а затем удаляет *других* параметра.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)