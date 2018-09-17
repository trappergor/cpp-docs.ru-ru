---
title: codecvt_utf8_utf16 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- codecvt/std::cvt_utf8_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 272e4007c3421613acfecc95fdd9548663dfceeb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719996"
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16

Представляет аспект [языкового стандарта](../standard-library/locale-class.md), который выполняет преобразование между расширенными символами в кодировке UTF-16 и потоком байтов в кодировке UTF-8.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Параметры

*Elem*<br/>
Тип двухбайтового элемента.

*Maxcode*<br/>
Максимальное количество символов для аспекта языкового стандарта.

*Режим*<br/>
Сведения о конфигурации для аспекта языкового стандарта.

## <a name="remarks"></a>Примечания

Поток байтов может записываться в двоичный файл или текстовый файл.

## <a name="requirements"></a>Требования

Заголовок: \<codecvt >

Пространство имен: std
