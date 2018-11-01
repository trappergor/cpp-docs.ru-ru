---
title: Ошибка средств компоновщика LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: 71aba1f20cfaf5b6b9ec33d43ebde594e381921f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594094"
---
# <a name="linker-tools-error-lnk1179"></a>Ошибка средств компоновщика LNK1179

Недопустимый или поврежденный файл: повторяющийся COMDAT «имя_файла»

Модуль объекта содержит два или более COMDAT с тем же именем.

Эта ошибка может возникнуть при использовании [/H](../../build/reference/h-restrict-length-of-external-names.md), который ограничивает длину внешних имен, и [/Gy](../../build/reference/gy-enable-function-level-linking.md), какие пакеты функций COMDAT.

## <a name="example"></a>Пример

В следующем коде `function1` и `function2` идентичны в первые восемь символов. Компиляция с **/Gy** и **/H8** возникает ошибка компоновки.

```
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```