---
title: codecvt_utf8
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf8
helpviewer_keywords:
- codecvt_utf8 class
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
ms.openlocfilehash: 3e3ddeccac2c18eedb96746f1c442c6b42349783
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405255"
---
# <a name="codecvtutf8"></a>codecvt_utf8

Представляет аспект [языкового стандарта](../standard-library/locale-class.md), который выполняет преобразование между расширенными символами в кодировке UCS-2 или UCS-4 и потоком байтов в кодировке UTF-8.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>
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

Заголовок: \<codecvt > \

Пространство имен: std
