---
title: codecvt_utf8_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::cvt_utf8_utf16
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
ms.openlocfilehash: 879ebe6a75d76a84ef4250b95c41e02eccba5517
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458642"
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16

Представляет аспект [языкового стандарта](../standard-library/locale-class.md), который выполняет преобразование между расширенными символами в кодировке UTF-16 и потоком байтов в кодировке UTF-8.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Параметры

*Elem*\
Тип двухбайтового элемента.

*макскоде*\
Максимальное количество символов для аспекта языкового стандарта.

*Режима*\
Сведения о конфигурации для аспекта языкового стандарта.

## <a name="remarks"></a>Примечания

Поток байтов может записываться в двоичный файл или текстовый файл.

## <a name="requirements"></a>Требования

Заголовок: \<codecvt >

Пространство имен: STD
