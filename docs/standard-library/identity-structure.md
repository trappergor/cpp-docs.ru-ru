---
title: Структура identity | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- utility/std::identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83180020c20f78c16af0b1b33bada91936b6af9b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="identity-structure"></a>Структура identity

Структура, предоставляющая определение типа как параметр шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };
```
### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`left`|Значение, которое необходимо идентифицировать.|

## <a name="remarks"></a>Примечания

Класс содержит определение открытого типа `type`, которое совпадает с типом параметра-шаблона. Он используется в сочетании с функцией шаблона [forward](../standard-library/utility-functions.md#forward) для проверки того, что параметр функции имеет требуемый тип.

Для обеспечения совместимости со старым кодом этот класс также определяет функцию identity `operator()`, которая возвращает свой аргумент `left`.

## <a name="requirements"></a>Требования

**Заголовок:** \<utility>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<utility>](../standard-library/utility.md)<br/>
