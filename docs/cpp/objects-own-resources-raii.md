---
title: Собственные ресурсы объекта (RAII)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
ms.openlocfilehash: a10d6c2177c391ead6065767994b09fb6236ee3a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593616"
---
# <a name="objects-own-resources-raii"></a>Собственные ресурсы объекта (RAII)

Убедитесь, что объекты, собственные ресурсы. Этот принцип — также называется «приобретения ресурсов инициализации» или «RAII.»

## <a name="example"></a>Пример

Передача каждого «new» объекта в качестве аргумента конструктора для другой именованный объект, который им владеет (почти всегда unique_ptr).

```cpp
void f() {
    unique_ptr<widget> p( new widget() );
    my_class x( new widget() );
    // ...
} // automatic destruction and deallocation for both widget objects
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"
```

Всегда следуют сразу передайте любой новый ресурс в другой объект, который им владеет.

```cpp
void g() {
    other_class y( OpenFile() );
    // ...
} // automatic closing and release for file resource
  // automatic exception safety, as if "finally { y.file.dispose(); }"
```

## <a name="see-also"></a>См. также

[Возвращение к C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Справочник по языку C++](../cpp/cpp-language-reference.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)