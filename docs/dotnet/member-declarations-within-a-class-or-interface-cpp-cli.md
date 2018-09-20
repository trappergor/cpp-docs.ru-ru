---
title: Объявления членов в пределах класса или интерфейса (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- members, declaration syntax
- class members, declaration syntax
ms.assetid: 95d312a4-198b-46f0-b8f5-15253807c55e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 80b872b4c614677c05b0d28b821d3a48255905c5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430642"
---
# <a name="member-declarations-within-a-class-or-interface-ccli"></a>Объявления членов в пределах класса или интерфейса (C++/CLI)

Объявление свойства и операторы была значительно переработана, из управляемых расширений для C++ для Visual C++, скрытие основные сведения о реализации, которые были видны в управляемых расширениях. Также были изменены объявлений событий.

В категории изменения, не поддерживаются управляемыми расширениями, статические конструкторы, которые теперь могут быть определенные вне строки (они были обязательно быть определен как встроенный в управляемых расширениях) и понятие делегирующий конструктор был введен.

## <a name="in-this-section"></a>В этом разделе

[Объявление свойства](../dotnet/property-declaration.md)<br/>
Рассматриваются изменения в объявлении свойства.

[Объявление индекса свойства](../dotnet/property-index-declaration.md)<br/>
Рассматриваются изменения в объявлении индексированных свойств.

[Делегаты и события](../dotnet/delegates-and-events.md)<br/>
Рассматриваются изменения в синтаксисе объявления делегатов и событий.

[Запечатывание виртуальной функции](../dotnet/sealing-a-virtual-function.md)<br/>
Рассматриваются изменения в синтаксисе запечатывание функции.

[Перегруженные операторы](../dotnet/overloaded-operators.md)<br/>
Рассматриваются изменения в перегрузку операторов.

[Изменение операторов преобразования](../dotnet/changes-to-conversion-operators.md)<br/>
Рассматриваются изменения в операторы преобразования.

[Явное переопределение элемента интерфейса](../dotnet/explicit-override-of-an-interface-member.md)<br/>
Рассматриваются изменения в метод явного переопределения члена интерфейса.

[Закрытые виртуальные функции](../dotnet/private-virtual-functions.md)<br/>
Рассматриваются изменения в способ обработки закрытые виртуальные функции в производных классах.

[Компоновка статической константы Int больше не является литералом](../dotnet/static-const-int-linkage-is-no-longer-literal.md)<br/>
Рассматриваются изменения в способ `static const` связывания целочисленных членов и явного объявления констант с использованием нового `literal` ключевое слово.

## <a name="see-also"></a>См. также

[Основы миграции C++/CLI](../dotnet/cpp-cli-migration-primer.md)