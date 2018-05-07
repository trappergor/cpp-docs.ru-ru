---
title: Класс exception | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- exception
dev_langs:
- C++
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 713600a72886b713c58c4a449c6f5270a3ccfe9a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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

Параметр `int` позволяет указать, что память не должна выделяться. Значение параметра `int` игнорируется.

> [!NOTE]
> Конструкторы `exception(const char* const &message)` и `exception(const char* const &message, int)` являются расширениями Майкрософт для стандартной библиотеки C++.

## <a name="example"></a>Пример

Примеры использования стандартных классов исключений, которые наследуют из класса `exception`, см. в любом классе, определенном в [\<stdexcept>](../standard-library/stdexcept.md).

## <a name="requirements"></a>Требования

**Заголовок:** \<exception>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
