---
title: codecvt_utf16 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9614303e62d3d1ca374eecca8c04cc30a7f94106
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109801"
---
# <a name="codecvtutf16"></a>codecvt_utf16

Представляет аспект [языкового стандарта](../standard-library/locale-class.md), который выполняет преобразование между расширенными символами в кодировке UCS-2 или UCS-4 и потоком байтов в кодировке UTF-16LE или UTF-16BE.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Параметры

*Elem*<br/>
Тип двухбайтового элемента.
*Maxcode*<br/>
Максимальное количество символов для аспекта языкового стандарта.
*Режим*<br/>
Сведения о конфигурации для аспекта языкового стандарта.

## <a name="remarks"></a>Примечания

Этот класс шаблона выполняет преобразование между расширенными символами в кодировке UCS-2 или UCS-4 и потоком байтов в кодировке UTF-16LE, если Mode & little_endian, или в кодировке UTF-16BE в ином случае.

Поток байтов должен записываться в двоичный файл; при записи в текстовый файл он может быть поврежден.

## <a name="requirements"></a>Требования

Заголовок: \<codecvt> Пространство имен: std