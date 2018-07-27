---
title: Класс wbuffer_convert | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 364ae6c544f58f09208cefeec9d3984de35120e1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965220"
---
# <a name="wbufferconvert-class"></a>Класс wbuffer_convert

Описывает буфер потока, который управляет передачей элементов в буфер потока байтов и из него.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
 : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*codecvt*|Аспект [языкового стандарта](../standard-library/locale-class.md), представляющий объект преобразования.|
|*Elem*|Тип двухбайтового элемента.|
|*Признаки*|Признаки, связанные с *Elem*.|

## <a name="remarks"></a>Примечания

Этот класс шаблона описывает буфер потока, который управляет передачей элементов типа `_Elem`, признаки символов которого описываются с помощью класса `Traits`, в буфер потока байтов типа `std::streambuf` и из него.

Преобразование между последовательностями значений `Elem` и многобайтовыми последовательностями выполняется объектом класса `Codecvt<Elem, char, std::mbstate_t>`, который соответствует требованиям аспекта стандартного преобразования кода `std::codecvt<Elem, char, std::mbstate_t>`.

Объект этого класса шаблона сохраняет:

- указатель на базовый буфер потока байтов;

- Указатель на выделенный объект преобразования (освобождается при уничтожении объекта [wbuffer_convert](../standard-library/wbuffer-convert-class.md))
