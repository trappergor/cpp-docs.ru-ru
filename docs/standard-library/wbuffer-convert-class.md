---
title: Класс wbuffer_convert
ms.date: 11/04/2016
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
ms.openlocfilehash: 8de0091af93120290105ce7603fae5acff257b76
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688542"
---
# <a name="wbuffer_convert-class"></a>Класс wbuffer_convert

Описывает буфер потока, который управляет передачей элементов в буфер потока байтов и из него.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
    : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Codecvt*|Аспект [языкового стандарта](../standard-library/locale-class.md), представляющий объект преобразования.|
|*Elem*|Тип двухбайтового элемента.|
|*Признаки*|Признаки, связанные с *Elem*.|

## <a name="remarks"></a>Заметки

Этот шаблон класса описывает буфер потока, который управляет передачей элементов типа `_Elem`, признаки символов которых описаны в классе `Traits`, в буфер потока байтов типа `std::streambuf` и обратно.

Преобразование между последовательностями значений `Elem` и многобайтовыми последовательностями выполняется объектом класса `Codecvt<Elem, char, std::mbstate_t>`, который соответствует требованиям аспекта стандартного преобразования кода `std::codecvt<Elem, char, std::mbstate_t>`.

Объект этого шаблона класса хранит:

- указатель на базовый буфер потока байтов;

- Указатель на выделенный объект преобразования (освобождается при уничтожении объекта [wbuffer_convert](../standard-library/wbuffer-convert-class.md))
