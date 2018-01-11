---
title: "Объявления членов в пределах класса или интерфейса (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- members, declaration syntax
- class members, declaration syntax
ms.assetid: 95d312a4-198b-46f0-b8f5-15253807c55e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 96a12f544babbf188c3718bcd49233472ad0d002
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="member-declarations-within-a-class-or-interface-ccli"></a>Объявления членов в пределах класса или интерфейса (C++/CLI)
Объявление свойств и операторов был широко переработан при переходе от управляемых расширений для C++ к Visual C++, скрытие основные сведения о реализации, которые были видны в управляемых расширениях. Также были изменены объявлений событий.  
  
 В категории изменений, не поддерживаются управляемыми расширениями, статические конструкторы, которые теперь могут быть определенным вне строки (они были обязательно быть определен как встроенный в управляемых расширениях) и понятие делегирующий конструктор представлена.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Объявление свойства](../dotnet/property-declaration.md)  
 Рассматриваются изменения в объявлении свойства.  
  
 [Объявление индекса свойства](../dotnet/property-index-declaration.md)  
 Рассматриваются изменения в объявлении индексированных свойств.  
  
 [Делегаты и события](../dotnet/delegates-and-events.md)  
 Рассматриваются изменения в синтаксисе объявления делегатов и событий.  
  
 [Запечатывание виртуальной функции](../dotnet/sealing-a-virtual-function.md)  
 Рассматриваются изменения в синтаксисе запечатывания функций.  
  
 [Перегруженные операторы](../dotnet/overloaded-operators.md)  
 Рассматриваются изменения в перегрузку операторов.  
  
 [Изменение операторов преобразования](../dotnet/changes-to-conversion-operators.md)  
 Рассматриваются изменения в операторы преобразования.  
  
 [Явное переопределение элемента интерфейса](../dotnet/explicit-override-of-an-interface-member.md)  
 Рассматриваются изменения в методах явного переопределения члена интерфейса.  
  
 [Закрытые виртуальные функции](../dotnet/private-virtual-functions.md)  
 Рассматриваются изменения в способ обработки закрытых виртуальных функций в производных классах.  
  
 [Компоновка статической константы Int больше не является литералом](../dotnet/static-const-int-linkage-is-no-longer-literal.md)  
 Рассматриваются изменения в способе `static const` связывания целочисленных членов и явного объявления констант с использованием нового `literal` ключевое слово.  
  
## <a name="see-also"></a>См. также  
 [Основы миграции C++/CLI](../dotnet/cpp-cli-migration-primer.md)