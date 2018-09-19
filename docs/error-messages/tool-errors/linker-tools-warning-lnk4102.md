---
title: Предупреждение средств компоновщика LNK4102 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4102
dev_langs:
- C++
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9daaffc4ddfa9a869c2e60e2c05dc2b7e296d94b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031870"
---
# <a name="linker-tools-warning-lnk4102"></a>Предупреждение средств компоновщика LNK4102

Экспорт деструктора удаления «имя»; образ может неправильно выполняться

Программа пытается экспортировать удаленный деструктор. Итоговый delete может произойти через границу DLL, таким образом, процесс может освободить память, он не владеет. Убедитесь, что данный символ не присутствует в DEF-файле и не имеет в качестве аргумента **/ИМПОРТ** или **/EXPORT** параметр в командной строке компоновщика.

Если библиотеки времени выполнения C, это сообщение можно игнорировать.