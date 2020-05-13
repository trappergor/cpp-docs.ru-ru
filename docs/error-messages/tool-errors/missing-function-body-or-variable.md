---
title: Отсутствует тело функции или переменная
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: 6d2ef22b90009d320485fb6fe3f7e308ae05c442
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173625"
---
# <a name="missing-function-body-or-variable"></a>Отсутствует тело функции или переменная

При использовании только прототипа функции компилятор может продолжить работу без ошибок, но компоновщик не может разрешить вызов адреса, так как код функции или переменное пространство не зарезервировано. Эта ошибка не появится, пока не будет создан вызов функции, которую компоновщик должен разрешить.

## <a name="example"></a>Пример

Вызов функции в Main приведет к возникновению ошибки LNK2019, поскольку прототип позволяет компилятору подумать, что функция существует.  Компоновщик обнаружит, что это не так.

```cpp
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example"></a>Пример

В C++убедитесь, что вы включили реализацию определенной функции для класса, а не только прототипа в определении класса. Если вы определяете класс за пределами файла заголовка, не забудьте включить имя класса перед функцией (`Classname::memberfunction`).

```cpp
// LNK2019_MFBV_2.cpp
// LNK2019 expected
struct A {
   static void Test();
};

// Should be void A::Test() {}
void Test() {}

int main() {
   A AObject;
   AObject.Test();
}
```

## <a name="see-also"></a>См. также раздел

[Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
