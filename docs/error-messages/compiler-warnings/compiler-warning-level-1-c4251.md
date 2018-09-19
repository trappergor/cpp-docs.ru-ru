---
title: Предупреждение компилятора (уровень 1) C4251 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad47d769dbfd09cc741be18598355dc34486bd54
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045696"
---
# <a name="compiler-warning-level-1-c4251"></a>Предупреждение компилятора (уровень 1) C4251

«Идентификатор»: класс «тип» должен иметь интерфейс dll для использования клиентами класса «тип2»

Чтобы свести к минимуму возможность повреждения данных при экспорте класс с [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), убедитесь, что:

- Все статические данные — доступ с помощью функций, которые экспортируются из библиотеки DLL.

- Нет встроенных методов класса могут изменять статические данные.

- Нет встроенных методов класса использовать функции CRT или другие функции библиотеки используют статические данные (см. в разделе [потенциальные ошибки передачи CRT объекты через границы DLL](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) Дополнительные сведения).

- Нет методов класса (вне зависимости от встраивания) можно использовать типы, где отличаются статические данные в экземпляров в EXE и DLL.

Экспортирование классов, определяя, библиотеки DLL, которая определяет класс с виртуальными функциями и функции, которые можно использовать для создания и удаления объектов типа, можно предотвратить.  Затем можно просто вызвать виртуальные функции в типе.

Дополнительные сведения об экспорте шаблонов см. в разделе [ http://support.microsoft.com/default.aspx?scid=KB; EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).

C4251 может игнорироваться при наследовании от типа в стандартной библиотеке C++, компиляция отладочного выпуска (**/MTd**), где сообщение об ошибке компилятора ссылается на _Container_base.

```
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```