---
title: Объявления и определения в C
ms.date: 11/04/2016
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
ms.openlocfilehash: d0dbd74dd54b6ee80fc1f02cf1cb07379a778be0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427967"
---
# <a name="c-declarations-and-definitions"></a>Объявления и определения в C

Объявление устанавливает связь между указанной переменной, функцией или типом и их атрибутами. В статье [Общие сведения об объявлениях](../c-language/overview-of-declarations.md) приводится синтаксис ANSI для нетерминального элемента `declaration`. В объявлении также определяется, где и когда возможен доступ к идентификатору ("компоновка" идентификатора). Дополнительные сведения о компоновке см. в статье [Время существования, область, видимость и компоновка](../c-language/lifetime-scope-visibility-and-linkage.md).

Определение переменной устанавливает те же связи, что и объявление, но также приводит к выделению памяти для переменной.

Например, функции `main`, `find` и `count` и переменные `var` и `val` определяются в одном исходном файле в следующем порядке:

```
int main() {}

int var = 0;
double val[MAXVAL];
char find( fileptr ) {}
int count( double f ) {}
```

Переменные `var` и `val` могут использоваться в функциях `find` и `count`; никакие дополнительные объявления не требуются. Однако в функции `main` эти имена не видны (доступ к ним невозможен).

## <a name="see-also"></a>См. также

[Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)