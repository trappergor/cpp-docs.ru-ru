---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: a84ca6da22825ca3fa7ab43e43a574fb05caa1a8
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689827"
---
# <a name="codecvt_utf16"></a>codecvt_utf16

Представляет аспект [языкового стандарта](../standard-library/locale-class.md), который выполняет преобразование между расширенными символами в кодировке UCS-2 или UCS-4 и потоком байтов в кодировке UTF-16LE или UTF-16BE.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Параметры

*Elem* \
Тип двухбайтового элемента.

*Макскоде* \
Максимальное количество символов для аспекта языкового стандарта.

*Режим* \
Сведения о конфигурации для аспекта языкового стандарта.

## <a name="remarks"></a>Заметки

Этот шаблон класса выполняет преобразование между расширенными символами в кодировке UCS-2 или UCS-4 и потоком байтов в кодировке UTF-16LE, если mode & little_endian или UTF-16BE в противном случае.

Поток байтов должен записываться в двоичный файл; при записи в текстовый файл он может быть поврежден.

## <a name="requirements"></a>Требования

Заголовок: \<codecvt >

Пространство имен: STD