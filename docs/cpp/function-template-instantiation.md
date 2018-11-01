---
title: Создание экземпляра шаблона функции
ms.date: 11/04/2016
helpviewer_keywords:
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
ms.openlocfilehash: c4667f5ae625468cdab428706ddaff92a1c1af33
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620939"
---
# <a name="function-template-instantiation"></a>Создание экземпляра шаблона функции

При первом вызове шаблона функции для каждого типа компилятор создает экземпляр. Каждый экземпляр представляет собой шаблонную функцию, специализированную для данного типа. Этот экземпляр будет вызваться каждый раз, когда функция используется для данного типа. Если имеется несколько одинаковых экземпляров, даже в различных модулях, в исполняемый файл будет помещен только один экземпляр.

В шаблонах функций преобразование аргументов функции разрешается для любых пар аргументов и параметров, в которых параметр не зависит от аргумента шаблона.

Можно явно создавать экземпляры шаблонов функций, объявляя шаблон с определенным типом в качестве аргумента. Например, приведенный ниже код допустим:

```cpp
// function_template_instantiation.cpp
template<class T> void f(T) { }

// Instantiate f with the explicitly specified template.
// argument 'int'
//
template void f<int> (int);

// Instantiate f with the deduced template argument 'char'.
template void f(char);
int main()
{
}
```

## <a name="see-also"></a>См. также

[Шаблоны функций](../cpp/function-templates.md)