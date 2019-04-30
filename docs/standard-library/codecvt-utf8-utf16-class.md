---
title: codecvt_utf8_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::cvt_utf8_utf16
helpviewer_keywords:
- codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
ms.openlocfilehash: 42c9c8643edc795748c1f12c5180471f281c4142
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405265"
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
