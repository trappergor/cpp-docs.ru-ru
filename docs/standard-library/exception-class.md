---
title: Класс exception | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- exception
dev_langs:
- C++
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec1cfe2be7f6a2172b6624f15cb3dcde4f0ba3c2
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957022"
---
# <a name="exception-class"></a>Класс exception

Этот класс служит базовым классом для всех исключений, создаваемых определенными выражениями и стандартной библиотекой C++.

## <a name="syntax"></a>Синтаксис

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
   };
```

## <a name="remarks"></a>Примечания

В частности, этот базовый класс является корнем стандартных классов исключений, определенных в [\<stdexcept>](../standard-library/stdexcept.md). Значение строки в C, возвращаемое объектом `what`, не указывается конструктором по умолчанию, но может быть определено конструкторами для некоторых производных классов как строка C для заданной реализации. Ни одна из функций-членов не создает исключение.

**Int** параметр позволяет указать, что нет памяти необходимо выделить. Значение **int** учитывается.

> [!NOTE]
> Конструкторы `exception(const char* const &message)` и `exception(const char* const &message, int)` являются расширениями Майкрософт для стандартной библиотеки C++.

## <a name="example"></a>Пример

Примеры использования стандартных классов исключений, которые наследуют из класса `exception`, см. в любом классе, определенном в [\<stdexcept>](../standard-library/stdexcept.md).

## <a name="requirements"></a>Требования

**Заголовок:** \<exception>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
