---
title: Класс exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: 5bef8190889ae00298760ea395fb524f557c2be2
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446828"
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

## <a name="remarks"></a>Remarks

В частности, этот базовый класс является корнем стандартных классов исключений, определенных в [\<stdexcept>](../standard-library/stdexcept.md). Значение строки в C, возвращаемое объектом `what`, не указывается конструктором по умолчанию, но может быть определено конструкторами для некоторых производных классов как строка C для заданной реализации. Ни одна из функций-членов не создает исключение.

Параметр **int** позволяет указать, что память не должна выделяться. Значение **int** не учитывается.

> [!NOTE]
> Конструкторы `exception(const char* const &message)` и `exception(const char* const &message, int)` являются расширениями Майкрософт для стандартной библиотеки C++.

## <a name="example"></a>Пример

Примеры использования стандартных классов исключений, которые наследуют из класса `exception`, см. в любом классе, определенном в [\<stdexcept>](../standard-library/stdexcept.md).
