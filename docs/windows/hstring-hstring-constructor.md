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
ms.openlocfilehash: 80af8f463d6cd1af631c6cb37c0239e7a9e85c3f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595889"
---
# <a name="hstringhstring-constructor"></a>Конструктор HString::HString

Инициализирует новый экземпляр класса **HString** класса.

## <a name="syntax"></a>Синтаксис

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

#### <a name="parameters"></a>Параметры

*HSTR*  
Дескриптор HSTRING.

*other*  
Существующий **HString** объекта.

## <a name="remarks"></a>Примечания

Первый конструктор инициализирует новый **HString** объект, который является пустым.

Второй конструктор инициализирует новый **HString** значение существующего *других* параметра, а затем удаляет *других* параметра.

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Класс HString](../windows/hstring-class.md)